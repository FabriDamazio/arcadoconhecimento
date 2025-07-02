---
Criado: 2025-01-06T10:54
Atualizado: 2025-05-23T17:24
Estudado: 2025-06-27T17:11
Links:
  - "[[SQL]]"
---
---
# SQL - Dates

Os banco de dados podem ter tipos de dados diferentes para representar datas. Em geral, os 3 tipos de dados mais usados para guardar data/tempo são:

- `DATE`: no formato YYYY-MM-DD
- `DATETIME`: no formato YYYY-MM-DD HH:MI:SS
- `TIMESTAMP`

Outros tipos de dados podem existir, assim como o formato de cada um pode ser diferente a depender do banco de dados.

# Formatando datas

Cada tipo de banco de dados possui diferentes comandos para formatar datas. 

### SQL SERVER  (MSSQL)

A partir do SQL Server 2012, temos a função `FORMAT` que permite formatar tanto valores númericos quanto datas. 

```sql

-- Função FORMAT
-- value é o valor a ser formatado
-- format é o formato a ser aplicado
-- culture é opicional e se não informado é usado o da sessão
FORMAT( value , format [ , culture ] )

-- Exemplo de uso
DECLARE @d AS DATE = '08/09/2024';

SELECT FORMAT(@d, 'd', 'en-US') AS 'US English',
       FORMAT(@d, 'd', 'en-gb') AS 'British English',
       FORMAT(@d, 'd', 'de-de') AS 'German',
       FORMAT(@d, 'd', 'zh-cn') AS 'Chinese Simplified (PRC)';

SELECT FORMAT(@d, 'D', 'en-US') AS 'US English',
       FORMAT(@d, 'D', 'en-gb') AS 'British English',
       FORMAT(@d, 'D', 'de-de') AS 'German',
       FORMAT(@d, 'D', 'zh-cn') AS 'Chinese Simplified (PRC)';

-- resultado
US English   British English  German      Simplified Chinese (PRC)
-----------  ---------------- ----------- -------------------------
8/9/2024     09/08/2024       09.08.2024  2024/8/9

US English              British English  German                    Chinese (Simplified PRC)
----------------------- ---------------- ------------------------  -------------------------
Friday, August 9, 2024  09 August 2024   Freitag, 9. August 2024   2024年8月9日
```

Os símbolos aceitos no parâmetro format devem ser consultados na documentação oficial.
### MySQL

Já no MySQL a função `FORMAT` é usada para formatar apenas valores numéricos. Para formatar datas é usado a função `DATE_FORMAT`.

```sql
-- função DATE_FORMAT
DATE_FORMAT(date, format)

-- Exemplo de uso

SELECT DATE_FORMAT(CURRENT_DATE,'%W');
-- Tuesday

SELECT DATE_FORMAT(CURRENT_DATE,'%W %D %M %Y ');
-- Tuesday 19th July 2016

SELECT DATE_FORMAT(CURRENT_DATE,'%W, %D %M %Y ');
-- Tuesday, 19th July 2016

SELECT DATE_FORMAT(CURRENT_DATE,'%d-%b-%y');
-- 19-Jul-16 

```

Os símbolos aceitos no parâmetro format devem ser consultados na documentação oficial.


---
## References

**SQL CRASH COURSE.** _SQL Date._ Disponível em: [https://sqlcrashcourse.com/sql-date/](https://sqlcrashcourse.com/sql-date/). Acesso em: 6 jan. 2025.

**DBLOAD.** _Format function in MSSQL and MySQL._ Disponível em: [https://www.dbload.com/articles/format-function-in-mssql-and-mysql.htm](https://www.dbload.com/articles/format-function-in-mssql-and-mysql.htm). Acesso em: 10 jan. 2025.