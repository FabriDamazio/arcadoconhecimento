# Visão Geral
```dataviewjs
const pages = dv.pages('"Arca do Conhecimento/Zettelkasten"');

const total = pages.length;
const ultimos7 = pages.filter(p => p.file.cday >= dv.date("today") - dv.duration("7 days")).length;
const ultimos15 = pages.filter(p => p.file.cday >= dv.date("today") - dv.duration("15 days")).length;
const ultimos30 = pages.filter(p => p.file.cday >= dv.date("today") - dv.duration("30 days")).length;

// Contar páginas com campo Estudado dentro dos últimos 1, 7, 15 e 30 dias
const estudados1 = pages.filter(p => p.Estudado && dv.date(p.Estudado) >= dv.date("today") - dv.duration("today")).length;
const estudados7 = pages.filter(p => p.Estudado && dv.date(p.Estudado) >= dv.date("today") - dv.duration("7 days")).length;
const estudados15 = pages.filter(p => p.Estudado && dv.date(p.Estudado) >= dv.date("today") - dv.duration("15 days")).length;
const estudados30 = pages.filter(p => p.Estudado && dv.date(p.Estudado) >= dv.date("today") - dv.duration("30 days")).length;

dv.table(
  ["Métrica", "Quantidade"],
  [
    ["Total de notas", total],
    ["Criadas nos últimos 7 dias", ultimos7],
    ["Criadas nos últimos 15 dias", ultimos15],
    ["Criadas nos últimos 30 dias", ultimos30],
    ["Estudadas hoje", estudados1],
    ["Estudadas nos últimos 7 dias", estudados7],
    ["Estudadas nos últimos 15 dias", estudados15],
    ["Estudadas nos últimos 30 dias", estudados30]
  ]
);
```

```dataview
CALENDAR file.cday
from "Arca do Conhecimento/Zettelkasten"
```


## As 30 notas que foram estudadas há mais tempo
```dataview
table without id
	file.link as "Título", dateformat(Estudado, "dd/MM/yyyy") as "Estudado em"
from "Arca do Conhecimento/Zettelkasten"
sort Estudado asc
limit 30
```

## Últimas 20 notas que foram criadas
```dataview
table without id
	file.link as "Título", dateformat(Criado, "dd/MM/yyyy") as "Criado em"
from "Arca do Conhecimento/Zettelkasten"
sort Criado desc
limit 20
```


