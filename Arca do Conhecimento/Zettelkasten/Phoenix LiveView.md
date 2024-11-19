19/11/2024 - 09:30
Status: #idea
Tags: [[Phoenix Framework]]

# Phoenix LiveView

Uma LiveView é um processo que recebe eventos, atualiza seu estado e retorna as diferenças do HTML para atualizar uma página.

## Ciclo de vida

Uma LiveView inicia com uma chamada HTTP que retorna o HTML da página.

![[LiveView1.png]]

 Em seguida ele estabelece uma conexão via web socket para receber os eventos

![[LiveView2.png]]

Ao receber um evento, ele atualiza seu estado e responde o que deve ser atualizado no HTML da página. A página é atualizada através do Javascript do LiveView que já esta incluso.

![[LiveView3.png]]
---

# References

PRAGMATIC STUDIO. First Controller. In: **Phoenix LiveView Programming**. Pragmatic Studio, 2024. Disponível em: [https://pragmaticstudio.com/courses/phoenix](https://pragmaticstudio.com/courses/phoenix). Acesso em: 04 nov. 2024.

PHOENIX. LiveView. _Phoenix LiveView Documentation_. Disponível em: [https://hexdocs.pm/phoenix_live_view/Phoenix.LiveView.html](https://hexdocs.pm/phoenix_live_view/Phoenix.LiveView.html). Acesso em: 19 nov. 2024.
