## Azure Data Factory

O Azure Data Factory) é um serviço de integração de dados baseado em nuvem que pode ajudar você a criar e agendar fluxos de trabalho orientados a dados. Você pode usar o Azure Data Factory para orquestrar a movimentação de dados e transformar dados em escala.

Há quatro etapas principais para criar e implementar um fluxo de trabalho controlado por dados na arquitetura do Azure Data Factory:

1. **Conectar e coletar**. Primeiro, ingira os dados para coletar todos os dados de diferentes fontes em um local centralizado.
2. **Transformar e enriquecer**. Em seguida, transforme os dados usando um serviço de computação como o Azure Databricks e o Azure HDInsight Hadoop.
3. **Fornecer CI/CD (integração e entrega contínuas) e publicar**. Dê suporte a CI/CD usando o GitHub e o Azure DevOps para entregar o processo de ETL incrementalmente antes de publicar os dados no mecanismo de análise.
4. **Monitorar**. Por fim, use o portal do Azure para monitorar o pipeline para atividades agendadas e para quaisquer falhas.

## Azure Data Lake

Um data lake é um repositório de dados armazenados no formato natural, geralmente como blobs ou arquivos.  O Azure Data Lake Storage combina um sistema de arquivos com uma plataforma de armazenamento para ajudá-lo a identificar rapidamente insights sobre seus dados.

- O Azure Data Lake Storage pode armazenar qualquer tipo de dados usando o formato nativo dos dados.
- A solução foi projetada principalmente para trabalhar com o Hadoop e todas as estruturas que usam o HDFS (Sistema de Arquivos Distribuído do Apache Hadoop).
- O Azure Data Lake Storage dá suporte a uma alta taxa de transferência para análise intensiva de entrada/saída e movimentação de dados.
- O Azure Data Lake Storage oferece suporte tanto ao controle de acesso baseado em função (RBAC) do Azure quanto às listas de controle de acesso (ACLs).
- O Azure Data Lake Storage utiliza os modelos de replicação de blobs do Azure. Esses modelos fornecem redundância de dados em um único datacenter com armazenamento com redundância local (LRS).

Saiba mais em [[Azure DataLake Storage Gen2]].

## Azure Databricks

O Azure Databricks é uma plataforma de Big Data e Machine Learning totalmente gerenciada e baseada em nuvem, que capacita os desenvolvedores a acelerar a IA e a inovação. O Azure Databricks é totalmente baseado no Apache Spark.

O Azure Databricks oferece três ambientes para desenvolver aplicativos com uso intensivo de dados: **Databricks SQL**, **Databricks Data Science & Engineering**, **Databricks Machine Learning**.

## Azure Synapse Analytics

O [Azure Synapse Analytics](https://azure.microsoft.com/products/synapse-analytics/) combina recursos de análise de Big Data, armazenamento de dados corporativos e integração de dados.

- Você envia consultas na forma de instruções Transact-SQL e o Azure Synapse Analytics as executa.
- O Azure Synapse usa uma tecnologia chamada [PolyBase](https://learn.microsoft.com/pt-br/sql/relational-databases/polybase/polybase-guide?) que permite recuperar e consultar dados de fontes relacionais e não relacionais. Você pode salvar os dados lidos como tabelas SQL no serviço do Azure Synapse.
- A arquitetura do Azure Synapse Analytics inclui um _nó de controle_ e um pool de _nós de computação_. 
## Azure Stream Analytics

O [Azure Stream Analytics](https://learn.microsoft.com/pt-br/azure/stream-analytics/stream-analytics-introduction) é um mecanismo de processamento de eventos complexo e análise em tempo real totalmente gerenciado (oferta de PaaS). Ele oferece a possibilidade de executar análises em tempo real em vários fluxos de dados de fontes como dados do dispositivo IoT, sensores, cliques e feeds de mídia social.





