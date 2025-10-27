---
Criado: 2025-01-14T09:05
Atualizado: 2025-07-30T16:51
Estudado: 2025-07-30T16:51
Links:
  - "[[SQL]]"
tags:
  - sql
  - programação
---
---
# SQL - comando DISTINCT

O comando DISTINCT pode ser usado em conjunto com o comando SELECT para recuperar registros únicos do banco de dados. Ele filtra os valores duplicados garantindo que as linhas retornadas tem valores únicos.

```sql
-- retorna os nomes únicos da tabela cliente
-- os registros duplicados são descartados.
SELECT DISTINCT nome FROM Clientes;
```

---
## References

**SQL CRASH COURSE.** _SQL DISTINCT._ Disponível em: [https://sqlcrashcourse.com/sql-distinct/](https://sqlcrashcourse.com/sql-distinct/). Acesso em: 14 jan. 2025.