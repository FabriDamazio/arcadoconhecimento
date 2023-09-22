O Azure Stream Analytics é um serviço para processamento de eventos complexos e análise de dados de streaming. O Stream Analytics é usado para: 

- Ingerir dados de uma _entrada_, como um hub de eventos do Azure, Hub IoT do Azure ou contêiner de blob de armazenamento do Azure.
- Processar os dados usando uma _consulta_ para selecionar, projetar e agregar valores de dados.
- Gravar os resultados em uma _saída_, como Azure Data Lake Gen 2, Banco de Dados SQL do Azure, Azure Synapse Analytics, Azure Functions, Hub de eventos do Azure, Microsoft Power BI ou outros.

## Azure Stream Analytics jobs and clusters

A maneira mais fácil de usar o Azure Stream Analytics é criar um Stream Analytics _job_, configurar suas entradas e saídas e definir a consulta que o trabalho usará para processar os dados. 

Se os requisitos do processo de fluxo forem complexos ou consumirem muitos recursos, você poderá criar um _cluster_ do Stream Analysis, que usa o mesmo mecanismo do job do Stream Analytics, mas em um tenant dedicado (para que seu processamento não seja afetado por outros clientes).

