![[monitorarrecursos.png]]

Sobre o [[Azure Monitor]].

## Sobre o Azure Monitor Log Workspaces

Um workspace é um recurso do Azure que serve como um limite administrativo ou local geográfico para armazenamento de dados. O workspace também é um contêiner em que você coleta e agrega dados.

- você pode isolar dados concedendo a diferentes direitos de acesso a usuários.
- os dados são organizados em tabelas. Cada tabela armazena diferentes tipos de dados e tem o próprio conjunto exclusivo de propriedades com base no recurso que está gerando os dados.
- Um workspace permite que você defina configurações como tier de preço, retenção e limite de dados.
- Suporta Azure RBAC.
-  são hospedados em clusters físicos. Por padrão, o sistema cria e gerencia esses clusters. Se o sistema ingerir mais de 500 GB de dados por dia, você criará os próprios clusters dedicados para seus workspaces para dar suporte a um maior controle e maior taxa de ingestão.

## Azure Workbooks

É um recurso do Azure Monitor. Fornece a criação de telas e dashboards através do portal da azure combinando diferentes dados e logs das aplicações.

# Azure Data Explorer

O Azure Data Explorer é uma plataforma de Big Data que ajuda você a analisar altos volumes de dados quase em tempo real. Possui recursos para configurar uma solução completa para ingerir e gerenciar seus dados, executar consultas e gerar visualizações.