---
Criado: 2025-09-16T12:29
Atualizado: 2025-09-16T12:29
Estudado: 2025-09-16T12:29
Links:
  - "[[Sistema de Mensageria (Message Broker)]]"
---
---
# Apache Kafka

É uma plataforma de código aberto para streaming de eventos de forma distribuída. É amplamente utilizado para pipelines dedados, streaming analytics e integração de dados.

## Como funciona

### Tópicos (topics)

São a principal abstração para armazenar e processar dados. É onde os logs (mensagens ou eventos) são armazenados em sequência e de forma imutável. Isso significa de cada novo log é feito o append aos logs existentes preservando toda a história, permitindo que as mudanças possam ser rastreadas através do tempo.

**Importante destacar que um tópico NÃO É UM TIPO DE FILA.** Quando um log é lido, ele não "sai" do tópico. Ele continua lá pelo período de retenção definido (7 dias por padrão). Essa abordagem permite repetibilidade e tolerância a falhas, pois os dados podem ser processados ​​várias vezes sem serem perdidos.

Nenhum formato específico para os dados dos logs é imposto. A resposabilidade de serializar e desserializar os dados é de responsabilidade dos produtores e consumidores. Os formatos mais comuns usados são:

- JSON: simples, legível por humanos e com amplo suporte.
- Apache Avro: serialização de dados binários que dependem de um schema externo armazenado em um schema registry.
- Protobuf: serialização de dados binários desenvolvido pelo Google. Baseado em schemas definidos em arquivos `.proto`.

Cada evento em um tópico é chamado de mensagem e consiste em três partes principais:

- KEY: identifica a origem do evento (como um ID de termostato ou um ID de usuário). Não é obrigatório mas permite o uso de outras funcionalidades do Kafka.
- Value: contém os dados reais (como a leitura da temperatura ou a ação de clique).
- Timestamp: um registro de data e hora, que marca a hora exata em que o evento foi produzido. Se não informado é fornecido automaticamente.
- HEADERS: um mapa de key-value usados para dar mais contexto dos dados.

### Partições (partitions)

Partições são a fundamentais para a escalabilidade e processamento distribuído do Kafka. Partições permitem dividir o log de um tópico em múltiplos logs menores (partições), distribuídos em diferentes nós, permitindo que o Kafka lide com volumes massivos de dados.

Relação da KEY da mensagem e sua ordenação:

- Dentro de uma partição: A ordem das mensagens é estritamente preservada. Elas são lidas na mesma sequência em que foram escritas.
- Entre partições: Não há garantia de ordem global. Mensagens com a mesma chave sempre vão para a mesma partição (via hashing da chave), garantindo ordem para essa chave.
- Mensagens sem chave: São distribuídas entre partições usando round-robin, o que balanceia a carga, mas perde a ordem para mensagens relacionadas.

### Brokers e Clusters

São os servidores do Kafka. Cada instância do servidor é um broker e ele pode rodar em máquinas físicas, instâncias em cloud ou até em Raspberry Pis. Cada broker armazena partições de tópicos, possibilitando a distribuição de armazenamento e processamento em múltiplos servidores, trazendo escalabilidade e resiliência. Um grupo de bokers formam um Kafka Cluster.

#### KRaft e Zookeeper

Um cluster do Kafka necessita de coordenar e gerenciar informações críticas entre seus brokers, como:

- **Gerenciamento de Metadados:** Armazenar qual broker é o líder de cada partição de cada tópico.
- **Descoberta de Serviços:** Permitir que os clientes (producers/consumers) descubram quais brokers estão ativos e onde os dados estão. 
- **Eleição de Líder:** Coordenar a eleição de um novo líder quando um broker falha.
- **Configuração:** Manter uma lista de controle de acesso (ACLs) e quotas.

Até a versão 3, a Kafka precisa de um ferramenta externa chamada Apache Zookeeper para essas tarefas. A partir da versão 4, a dependência externa do Zookeeper foi eliminada e internalizada  através da introdução do KRaft (Apache Kafka Raft). Isso trouxe simplificações na arquitetura do Kafka e ganhou de simplicidade e performance.

### Replicação (replication)

Para mitigar o risco da perda de dados uma partição pode ser replicada. Esse fator de replicação é configurável e sempre uma partição é a líder (leader) e as outras são as seguidores (followers). As mensagens sempre são escritas no leader e os followers and sempre se atualizando. Já a leitura em geral também é feita do líder mas em versões mais recentes é possível configurar para leitura das réplicas mais próximas para diminuir a latência.

Se um broker que contém uma partição líder tiver alguma indisponibilidade, uma nova partição em um broker saudável é eleita a nova líder e a operação continua normalmente.

### Producers

São aplicações que usam o Kafka e escrevem em seus tópicos. Para que a escrita seja possível, o Kafka expõe a Producer API e existem libs em praticamente todas as linguagens para simplificar seu uso. Em geral essas libs abstraem complexidades como escolher a qual partição enviar a mensagem, retires, acks e idempotência.

Os dados enviados pelos produtores são apenas bytes para o Kafka, não importando o formato de serialização. Existem serializadores build-in para tipos primitivos comum e para dados mais estuturados pode ser usado o Schema Registry.

### Consumers

São aplicações lêem dados de tópicos Kafka.  

---
## References