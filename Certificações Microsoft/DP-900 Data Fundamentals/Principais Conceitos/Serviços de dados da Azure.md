Alguns dos serviços de nuvem mais usados para dados estão descritos abaixo.

## Azure SQL

É o nome da família de soluções de banco de dados relacionais baseadas no Microsoft SQL Server.
Os serviços baseados nele são:

- **Azure SQL Database**: um banco de dados de PaaS (plataforma como serviço) totalmente gerenciado.
- **Azure SQL Managed Instance**:  uma instância hospedada do SQL Server com manutenção automatizada, que permite uma configuração mais flexível do que o BD de SQL do Azure.
- **Azure SQL VM**: uma máquina virtual com uma instalação do SQL Server, permitindo a máxima capacidade de configuração com total responsabilidade de gerenciamento.

## Azure Database for open-source relational databases

A Azure inclui serviços para alguns bancos de dados relacionais de código aberto, como:

- **Azure Database for MySQL**
- **Azure Database for MariaDB**
- **Azure Database for PostgreSQL**

## Azure Cosmos DB

O Azure Cosmos DB é um sistema de banco de dados não relacional (_NoSQL_) que permite armazenar e gerenciar dados como documentos JSON, pares de chave-valor, famílias de colunas e grafos.

## Azure Storage

Permite armazenar dados em:

- **Blob containers**: para arquivos binários.
- **File shares**: compartilhamentos de arquivos de rede.
- **Tables**:  armazenamento de chave-valor para aplicativos que precisam ler e gravar valores de dados rapidamente.

## Azure Data Factory

É um serviço que permite definir e agendar pipelines de dados para transferir e transformar dados. Você pode integrar seus pipelines a outros serviços da Azure, possibilitando a ingestão de dados de armazenamentos de dados, o processamento dos dados  e a manutenção dos resultados em outro armazenamento de dados.

**Usado por engenheiros de dados para criar soluções de ETL** (_extração_, _transformação_ e _carregamento_) que preenchem os armazenamentos de dados analíticos com os dados de sistemas transacionais.

## Azure Synapse Analytics

É uma solução de análise de dados abrangente e unificada que oferece uma interface de serviço única para diversos recursos de análise, como:

- **Pipelines**: baseado na mesma tecnologia do Azure Data Factory.
- **SQL**: banco de dados.
- **Apache Spark**: um sistema de processamento de dados distribuído de código aberto.
- **Azure Synapse Data Explorer**: uma solução de análise de dados de alto desempenho que é otimizada para consultas em tempo real de dados de log e telemetria usando a KQL.
- 
## Azure Databricks

Combina a plataforma de processamento de dados Apache Spark com a semântica de banco de dados SQL e uma interface de gerenciamento integrada para permitir análises de dados em larga escala.

Os engenheiros de dados podem criar armazenamentos de dados analíticos e os analistas de dados podem usar o suporte nativo a notebooks para consultar e visualizar dados.

## Azure HDInsight

É um serviço do Azure que fornece clusters hospedados no Azure para tecnologias de processamento de Big Data do Apache, como:

- **Apache Spark**:  um sistema de processamento de dados distribuído.
- **Apache Hadoop**: um sistema distribuído que usa trabalhos _MapReduce_ para processar grandes volumes de dados com eficiência em vários nós de cluster.
- **Apache HBase**: um sistema de código aberto para armazenamento e consulta de dados NoSQL em larga escala.
- - **Apache Kafka** – um agente de mensagens para processamento de fluxo de dados.
- 
## Azure Stream Analytics

É um mecanismo de processamento de fluxo em tempo real que captura um fluxo de dados de uma entrada, aplica uma consulta para extrair e manipular os dados dele e grava os resultados em uma saída para análise ou processamento adicional.

## Azure Data Explorer

É um serviço independente que oferece a mesma consulta de alto desempenho de dados de log e telemetria que o runtime do Azure Synapse Data Explorer do Azure Synapse Analytics.

Os analistas de dados podem usar para consultar e analisar dados que incluem um atributo de carimbo de data/hora (como arquivos de log e dados de telemetria da _IoT_).

## Microsoft Purview

Solução corporativa para governança e descoberta de dados. Usado para criar um mapa de seus dados e acompanhar a linhagem de dados em várias fontes de dados e sistemas, permitindo encontrar dados confiáveis para análise e relatórios.


## Microsoft Power BI

Plataforma para modelagem e geração de relatórios de dados analíticos que é usada por analistas de dados na criação e no compartilhamento de visualizações de dados interativas.