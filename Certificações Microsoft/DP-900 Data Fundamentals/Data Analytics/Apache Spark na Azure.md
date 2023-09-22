Apache Spark é uma estrutura de processamento distribuído para análise de dados em larga escala. Você pode usar o Spark no Microsoft Azure nos seguintes serviços:

- Azure Synapse Analytics
- Azure Databricks
- Azure HDInsight

Para processar dados de streaming no Spark, você pode usar a biblioteca  _Structured Streaming_. É uma ótima opção para análise em tempo real quando você precisa incorporar dados de streaming em um repositório de dados analíticos ou data lake baseado no Spark.

## Delta Lake

Delta Lake é uma camada de armazenamento de código aberto que adiciona suporte para consistência transacional, aplicação de esquema e outros recursos comuns de data warehouse ao armazenamento de data lake. Ele também unifica o armazenamento para dados em lote e streaming e pode ser usado no Spark para definir tabelas relacionais para processamento em lotes e em fluxo (streaming).

Azure Synapse Analytics e Azure Databricks incluem suporte para Delta Lake.