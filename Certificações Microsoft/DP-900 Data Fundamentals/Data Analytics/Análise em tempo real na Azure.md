A Azure oferece suporte a várias tecnologias que você pode usar para implementar análises em tempo real de dados de streaming, como:

- **Azure Stream Analytics**: uma solução de plataforma como serviço (PaaS) que você pode usar para definir _streaming jobs_ que ingerem dados de uma fonte de streaming e gravam os resultados em uma saída.
- **Spark Structured Streaming**: uma biblioteca de código aberto que permite desenvolver soluções de streaming complexas em serviços baseados no Apache Spark, incluindo o **Azure Synapse Analytics**, o **Azure Databricks** e o **Azure HDInsight**.
- **Azure Data Explorer**: um serviço de análise e banco de dados de alto desempenho otimizado para ingestão e consulta de dados em lote ou streaming com um elemento de série temporal e que pode ser usado como um serviço autônomo do Azure ou como um tempo de execução do **Azure Synapse Data Explorer** em um espaço de trabalho do Azure Synapse Analytics.

## Fontes (sources) para processamento de fluxo (streaming)

Os serviços a seguir são comumente usados para ingerir dados para processamento de fluxo:

- **Hubs de Eventos do Azure**: um serviço de ingestão de dados que você pode usar para gerenciar filas de dados de eventos, garantindo que cada evento seja processado em ordem, exatamente uma vez.
- **Hub IoT do Azure**: um serviço de ingestão de dados semelhante aos Hubs de Eventos do Azure, mas otimizado para gerenciar dados de eventos de dispositivos da _Internet das Coisas_ (IoT).
- **Azure Data Lake Store Gen 2**: um serviço de armazenamento altamente escalonável que é frequentemente usado em cenários de _processamento em lotes_, mas que também pode ser usado como fonte de dados de streaming.
- **Apache Kafka**: uma solução de ingestão de dados de código aberto que é comumente usada em conjunto com o Apache Spark. Você pode usar o Azure HDInsight para criar um cluster Kafka.

## Coletores (sinks) para processamento de fluxo (streaming)

A saída do processamento de fluxo geralmente é enviada para os seguintes serviços:

Hubs de Eventos do Azure: usados para enfileirar os dados processados para processamento posterior.
Azure Data Lake Store Gen 2 ou Azure blob storage: usados para manter os resultados processados como um arquivo.
Azure SQL Database ou Azure Synapse Analytics, ou Azure Databricks: usados para manter os resultados processados em uma tabela de banco de dados para consulta e análise.
Microsoft Power BI: usado para gerar visualizações de dados em tempo real em relatórios e painéis.