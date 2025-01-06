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

-- além do operador de igualdade, outros operadores de comparação são suportados
  -- != (diferente)
  -- <> (diferente)
  -- < (menor)
  -- <= (menor ou igual)
  -- > (maior)
  -- >= (maior ou igual)

-- Mais de uma condição pode ser informada no WHERE usando AND ou OR.
SELECT nome FROM clientes WHERE nome='Luciana' AND sobrenome='Garcia';

-- Também é possível usar o operador IN
SELECT nome FROM clientes WHERE nome IN ('Garcia', 'Reis', 'Damazio');

-- o operador NOT para recuperar registros que NÃO atendem um critério
SELECT nome FROM clientes WHERE nome NOT IN  ('Garcia', 'Damazio');

-- o operador LIKE permite filtrar por padrões de texto.
-- podemos especificar o wildcard % para ele dar match em qualquer padrão de texto que venha antes ou depois da string
SELECT nome FROM clientes WHERE nome like 'Lu%'

-- caso seja necessário dar match em um número exato de caracteres, o wildcard _ (underscore) pode ser usado com a quatidade exata de caracteres.
SELECT nome FROM clientes WHERE nome like 'Lu_____'

```


---

# References

**SQL CRASH COURSE.** _SQL WHERE Equals._ Disponível em: [https://sqlcrashcourse.com/sql-where-equals/](https://sqlcrashcourse.com/sql-where-equals/). Acesso em: 06 jan. 2025.