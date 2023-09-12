Em um banco de dados relacional, você modelará coleções de entidades do mundo real na forma de tabelas.

Uma tabela contém linhas e cada linha representa uma instância de uma entidade (um produto, um cliente ou qualquer outra coisa).

As tabelas relacionais são um formato para dados estruturados e cada linha de uma tabela tem as mesmas colunas e cada uma delas

armazena dados de um tipo de dados específico.

## Normalização

A normalização é um termo usado para um processo de design de esquema que minimiza a duplicação de dados e impõe a integridade dos dados.

Uma definição simples para fins práticos é:

- Separar cada entidade em sua própria tabela.

- Separar cada atributo discreto em sua própria coluna.

- Identificar exclusivamente cada instância de entidade (linha) usando uma chave primária.

- Usar colunas de chave estrangeira para vincular entidades relacionadas.

## Linguagem SQL

SQL significa Linguagem de Consulta Estruturada e é usada para se comunicar com um banco de dados relacional. Ele é a linguagem padrão para sistemas de gerenciamento de banco de dados relacional.

O SQL foi originalmente padronizado pelo ANSI (American National Standards Institute) em 1986 e pela ISO (Organização Internacional de Normalização) em 1987. Desde então, o padrão foi estendido várias vezes, pois os fornecedores de banco de dados relacional adicionaram novos recursos aos sistemas. Além disso, a maioria dos fornecedores de banco de dados inclui as próprias extensões proprietárias que não fazem parte do padrão, o que resultou em uma variedade de dialetos do SQL.

Alguns dialetos populares do SQL incluem:

- T-SQL (Transact-SQL). Essa versão do SQL é usada pelo Microsoft SQL Server e pelos serviços de SQL do Azure.

- pgSQL. Esse é o dialeto que tem extensões implementadas no PostgreSQL.

- PL/SQL. Esse é o dialeto usado pela Oracle. PL/SQL significa Procedural Language/SQL.

### Tipos de instrução SQL

Instruções SQL são agrupadas em três grupos lógicos principais:

- DDL (linguagem de definição de dados): usada para criar, modificar e remover tabelas e outros objetos em um banco de dados.

- DCL (linguagem de controle de dados): usada para gerenciar o acesso a objetos em um banco de dados, concedendo, negando ou revogando permissões a usuários ou grupos específicos.

- DML (linguagem de manipulação de dados): permitem recuperar (consultar) dados, inserir novas linhas ou modificar linhas existentes.

## View (Exibição)

Uma View (exibição) é uma tabela virtual com base no conjunto de resultados de uma consulta SELECT.

## Stored Procedure

Define instruções SQL que podem ser executadas sob comando. São usados para encapsular lógica programática de ações em um banco de dados.

## Índice (index)

Um índice ajuda a otimizar a pesquisa dados em uma tabela. Quando você cria um índice em um banco de dados, especifica uma coluna da tabela e o índice contém uma cópia desses dados em uma ordem classificada, com ponteiros para as linhas correspondentes na tabela. Quando o usuário executa uma consulta que especifica essa coluna na cláusula WHERE, o sistema de gerenciamento de banco de dados pode usar esse índice para buscar os dados mais rapidamente do que se precisasse examinar toda a tabela, linha por linha.