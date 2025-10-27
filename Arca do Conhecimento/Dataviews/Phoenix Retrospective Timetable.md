Níveis: 🔴 🟡 🟠 🔵 🟢

| Conceito                            | Última revisão | Nível |
| :---------------------------------- | :------------: | :---: |
| **FUNDAMENTOS**                     |                |       |
| Estrutura de projeto                |                |       |
| Router                              |                |       |
| Controllers                         |                |       |
| CoreComponents                      |                |       |
| Templates HEEx                      |                |       |
| **REQUEST LIFECYCLE**               |                |       |
| Plugs                               |                |       |
| Conn struct                         |                |       |
| Error handling (http)               |                |       |
| **CONTEXTS**                        |                |       |
| Context pattern                     |                |       |
| Schema vs Context reponsability     |                |       |
| Boundary design                     |                |       |
| **ECTO**                            |                |       |
| Schemas                             |                |       |
| Migrations                          |                |       |
| Changesets                          |                |       |
| Queries                             |                |       |
| Transactions                        |                |       |
| **AUTHENTICATION**                  |                |       |
| mix phx.gen.auth                    |                |       |
| Session management                  |                |       |
| Password hashing                    |                |       |
| **LIVEVIEW**                        |                |       |
| Liveview lifecycle                  |                |       |
| State management (assigns)          |                |       |
| Form handling                       |                |       |
| File uploads                        |                |       |
| JS commands e hooks                 |                |       |
| **ASSETS e STYLING**                |                |       |
| Tailwind integration                |                |       |
| DaisyUI                             |                |       |
| Asset management (css, js, statics) |                |       |
| Layouts                             |                |       |
| **DEPLOYMENT**                      |                |       |
| mix release                         |                |       |
| environment config                  |                |       |
| database in production              |                |       |
| SSL/HTTPS setup                     |                |       |
| **TESTING**                         |                |       |
| Testing controllers                 |                |       |
| Testing contexts                    |                |       |
| Testing liveview                    |                |       |
| end-to-end testing                  |                |       |
| **APIs**                            |                |       |
| JSON API (format, error handling)   |                |       |
| API versioning                      |                |       |
| API auth                            |                |       |
| **OTHERS**                          |                |       |
| Generators                          |                |       |

## As 30 notas sobre Phoenix que foram estudadas há mais tempo
```dataview
table without id
	file.link as "Título", dateformat(Estudado, "dd/MM/yyyy") as "Estudado em"
from "Arca do Conhecimento/Zettelkasten"
where contains(tags, "phoenix")
sort Estudado asc
limit 30
```

## As últimas 20 notas sobre Phoenix que foram criadas
```dataview
table without id
	file.link as "Título", dateformat(Criado, "dd/MM/yyyy") as "Criado em"
from "Arca do Conhecimento/Zettelkasten"
where contains(tags, "phoenix")
sort Criado desc
limit 20
```