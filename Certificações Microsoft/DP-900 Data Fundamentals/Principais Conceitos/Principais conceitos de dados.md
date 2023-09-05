Os dados são uma coleção de fatos, como números, descrições e observações usados para registrar informações.

Podemos classificar os dados como _estruturados_, _semiestruturados_ ou _não estruturados_.

## Estrutura dos dados
### Dados estruturados

Obedecem a um _esquema_ fixo, portanto, todos os dados têm os mesmos campos ou propriedades. Normalmente, o esquema para entidades de dados estruturados é _tabular_.

### Dados semiestruturados

Dados _semiestruturados_ são informações que têm alguma estrutura, mas que permitem alguma variação entre instâncias da entidade. Um formato comum para dados semiestruturados é o _JSON_.

### Dados não estruturados

Documentos, imagens, dados de áudio e vídeo e arquivos binários podem não ter uma estrutura específica. Esse tipo de dados é conhecido como dados _não estruturados_.

## Armazenamento de dados

Os dados são armazenados em formato estruturado, semiestruturado ou não estruturado. Há duas categoriais gerais de armazenamento:

- Banco de dados
- Armazenamento de arquivos

No caso dos bancos de dados eles podem ser relacionais ou não relacionais

### Banco de dados relacionais

Normalmente usado para armazenar dados estruturados em tabelas que possuem relação entre si através de identificados (chaves primárias).

### Bancos de dados não relacionais

Geralmente chamados de banco de dados NoSQL, os dados não possuem um esquema relacional de dados. Os quatro tipos mais comuns são:

- Banco de dados de chave-valor
- Banco de dados de documentos
- Banco de dados de família de colunas
- Banco de dados de grafo

## Processamento de dados transacionais

Um sistema de processamento de dados transacionais é o que a maioria das pessoas considera a principal função da computação empresarial. Um sistema transacional registra _transações_ que encapsulam eventos específicos que a organização deseja controlar.

O trabalho executado por sistemas transacionais é geralmente conhecido como Online Transactional Processing (OLTP).

As soluções OLTP dependem de um sistema de banco de dados no qual o armazenamento de dados é otimizado para operações de leitura e gravação e para fazer isso, os sistemas OLTP impõem transações compatíveis com a semântica conhecida como ACID:

- **Atomicidade**: cada transação é tratada como uma única unidade.
- **Consistência**: as transações só podem conduzir os dados do banco de dados de um estado válido para outro estado válido.
- **Isolamento**: as transações simultâneas não podem interferir entre si e devem resultar em um estado consistente do banco de dados.
- **Durabilidade**: quando uma transação tiver sido confirmada, ela permanecerá confirmada.

## Processamento de dados analíticos

O processamento de dados analíticos normalmente usa sistemas somente leitura (ou read-_mostly_) que armazenam grandes volumes de dados históricos ou métricas de negócios.

Uma arquitetura comum de análise de escala empresarial tem esta aparência:

![[Diagrama de arquitetura de analise de dados.png]]

1. Arquivos são armazenados em um data lake para análise.
2. Um processo ETL (extract, transform and load) copia dados de arquivos e banco de dados para um data warehouse otimizado pra leitura. Normalmente, o esquema de um data warehouse se baseia em tabelas de _fatos_ que contêm valores numéricos que você deseja analisar (por exemplo, valores de vendas), com tabelas de _dimensões_ relacionadas, que representam as entidades pelas quais você deseja medir (por exemplo, cliente ou produto).
3. Os dados no data warehouse podem ser agregados e carregados em um modelo OLAP (processamento analítico online) ou _cubo_. Valores numéricos agregados (_medidas_) de tabelas de fatos são calculados para interseções de _dimensões_ da tabelas de dimensões.
4. 1. Os dados no data lake, no data warehouse e no modelo analítico podem ser consultados para produzir relatórios, visualizações e dashboards.

Tipos diferentes de usuários podem executar trabalhos de análise de dados em diferentes estágios da arquitetura geral. Por exemplo:

- Os cientistas de dados podem trabalhar diretamente com arquivos de dados em um data lake para explorar e modelar os dados.
- Os Analistas de Dados podem consultar tabelas diretamente no data warehouse para produzir relatórios e visualizações complexos.
- Os usuários empresariais podem consumir dados previamente agregados em um modelo analítico na forma de relatórios ou painéis.