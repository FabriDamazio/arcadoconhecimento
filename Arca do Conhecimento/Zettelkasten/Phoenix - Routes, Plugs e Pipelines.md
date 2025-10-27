---
Criado: 2024-11-04T15:47
Atualizado: 2025-06-19T11:16
Estudado: 2025-08-06T11:37
Links:
  - "[[Phoenix Framework]]"
tags:
  - phoenix
---
---
# Phoenix - Routes, Plugs e Pipelines

### Plug

Um Plug é uma função ou módulo que recebe umas struct `%Conn{}`, realiza uma operação (transformação ou verificação) e retorna uma nova struct `%Conn{}` resultado desta operação. Ele é usado como uma "interceptador" da request para incluir ou verificar seus dados.

### Pipelines

É formada por um conjunto de um ou mais Plugs executados em uma sequência definida. Essa sequência pode ser atribuída a um scope (agrupamento de rotas) para que toda request passe por essa pipeline.

### Routes

Mapeiam URLs especificadas para funções de controle. Elas ficam dentro de um scope e são executadas logo após o fim da execução da pipeline.


![[Phoenix - Routes, Plugs e Pipelines.png]]


---
## References

PRAGMATIC STUDIO. Routes, Plugs, and Pipelines. In: **Phoenix LiveView Programming**. Pragmatic Studio, 2024. Disponível em: [https://pragmaticstudio.com/courses/phoenix](https://pragmaticstudio.com/courses/phoenix). Acesso em: 04 nov. 2024.