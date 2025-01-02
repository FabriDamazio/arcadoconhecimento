2025-01-02 - 14:06
Status: #idea
Tags: [[SQL]]

# SQL - comando WHERE

O comando WHERE permite filtrar os registros por um critério. Se ao nomear quais colunas quer no comando SELECT limita o número de colunas, o comando WHERE limita o número de linhas.

```SQL
-- os exemplos abaixo levam em conta uma tabela chamada clientes com as colunas nome, sobrenome e email.


-- seleciona todos registros da tabela clientes com o nome Luciana.
SELECT * FROM clientes WHERE nome='Luciana';

-- seleciona apenas a coluna nome de todos os registos da tabela de clientes com o nome Luciana.
SELECT nome FROM clientes WHERE nome='Luciana';

```




---

# References