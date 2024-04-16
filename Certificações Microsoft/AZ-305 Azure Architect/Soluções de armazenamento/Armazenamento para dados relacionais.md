## Azure SQL Database

Um banco de dados SQL do Azure é um serviço totalmente gerenciado. Não é necessário lidar com tarefas complexas de banco de dados, como configuração, gerenciamento, alta disponibilidade, ajustes e backups.

- É a única opção de implantação que dá suporte a cenários que exigem bancos de dados muito grandes (atualmente, até 100 TB) ou dimensionamento automático para cargas de trabalho imprevisíveis (sem servidor).
    
- É possível criar um **pool de banco de dados elástico do Banco de Dados SQL** para que todos os bancos de dados nele compartilhem o mesmo conjunto de recursos de computação e armazenamento. 

- Há duas opções de preços principais para o Banco de Dados SQL: DTU e vCore. Uma opção sem servidor também está disponível para um único banco de dados.

## Azure SQL Managed Instance

É um serviço totalmente gerenciado. Ela fornece uma instância do SQL Server, mas remove grande parte da sobrecarga de gerenciar uma máquina virtual. É possível usar a Instância Gerenciada de SQL para fazer migrações do tipo “lift-and-shift” para o Azure sem precisar reprojetar seus aplicativos.

## SQL Server on Azure Virtual Machines

É uma versão do SQL Server que é executada em uma VM (máquina virtual) do Azure. Esse serviço permite usar versões completas do SQL Server na nuvem sem precisar gerenciar as máquinas locais.

## Azure SQL Edge

É um mecanismo otimizado de banco de dados relacional criado para implantações de IoT e IOT Edge. É um aplicativo Linux em contêineres. O volume de memória de inicialização é inferior a 500 MB.

## Azure Cosmos DB and Table Storage

É possível guardar dados relacionais no Azure Table Storage e no Azure Cosmos DB (utilizando a Table API).
## Disponibilidade do banco de dados

|SQL Database vCore tiers|SQL Managed Instance DTU tiers|Database availability support|
|---|---|---|
|**General Purpose**|**Standard** or **Basic**|Oferece opções balanceadas de computação e armazenamento para cargas de trabalho de negócios |
|**Business Critical**|**Premium**|Atende aos requisitos de baixa latência e permite maior resiliência a falhas para aplicativos de negócios |
|**Hyperscale**|No applicable tier|Oferece um armazenamento altamente escalável e atende aos requisitos de escala de leitura de cargas de trabalho de negócios |

## Segurança para dados em descanso (rest), dados em movimento e dados em uso

|Estado de dados|Método de criptografia|Nível de criptografia|
|---|---|---|
|**Dados descanso** |TDE (Transparent Data Encryption)|Always encrypted|
|**Dados em movimento**|SSL/TLS (Secure Socket Layers e Transport Layer Security)|Always encrypted|
|**Dados em processo**|Mascaramento de dados dinâmicos|Dados específicos não são criptografados, mas os dados restantes são|
