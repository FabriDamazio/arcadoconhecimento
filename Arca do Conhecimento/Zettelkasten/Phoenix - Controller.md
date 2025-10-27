---
Criado: 2024-11-04T16:09
Atualizado: 2025-05-23T16:53
Estudado: 2025-08-06T11:36
Links:
  - "[[Phoenix Framework]]"
tags:
  - phoenix
---
---
# Phoenix - Controller

Um controller gerencia a lógica do processamento de uma request e envia a resposta apropriada. Ele recebe as informações da request através de uma rota e responde por exemplo com uma View ou um JSON.

Um fluxo comum de uma requisição: inicia no navegador -> passa pelos Plugs -> Chega ao Router e é roteada uma uma função em um Controller -> monta uma View -> envia a resposta ao navegador.

![[Phoenix - Controllers.png]]

---
## References

PHOENIX Framework. Controllers. HexDocs, 2024. Disponível em: [https://hexdocs.pm/phoenix/controllers.html](https://hexdocs.pm/phoenix/controllers.html). Acesso em: 04 nov. 2024.

PRAGMATIC STUDIO. First Controller. In: **Phoenix LiveView Programming**. Pragmatic Studio, 2024. Disponível em: [https://pragmaticstudio.com/courses/phoenix](https://pragmaticstudio.com/courses/phoenix). Acesso em: 04 nov. 2024.