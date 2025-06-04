---
Criado: 2024-11-19T09:30
Atualizado: 2025-05-23T16:59
Estudado: 2025-06-04T09:27
Links:
  - "[[Phoenix Framework]]"
---
---
# Phoenix LiveView

Uma LiveView é um processo que recebe eventos, atualiza seu estado e retorna as diferenças do HTML para atualizar uma página.

## Ciclo de vida

(1) - Uma LiveView inicia com uma chamada HTTP comum. 
(2 e 3) - A função mount é executada e logo em seguida a função render que retorna o HTML da página. Esta execução é conhecida como uma execução "desconectada" pelo fato que o processo o LiveView ainda não ter sido criado e a conexão websocket estabelecida.
(4) - O HTML completo é da página e o app.js são retornados.

![[LiveView1.png]]

(5 e 6) -  o javascript que é enviado junto com a pagina HTML inicial (app.js)  estabelece uma conexão via web socket com o processo criado exclusivamente para este LiveView.
(7 e 8) - as funções mount e logo em seguida render são executadas. Esta é uma execução conhecida como "conectada" porque acontece já no processo criado para este LiveView.
(9) - é retornado a parte estática e dinâmica da página HTML separada, para o que javascript possa atualizar o HTML quando necessário.

![[LiveView2.png]]

(10, 11 e 12) Ao receber um evento, a função handle_event correspondente é executada e ela atualiza o estado estado do processo e excuta a função render que responde o que deve ser atualizado no HTML da página. 
(13) A página é atualizada através do Javascript do LiveView que já esta incluso.

![[LiveView4.png]]
---
## References

PRAGMATIC STUDIO. First Controller. In: **Phoenix LiveView Programming**. Pragmatic Studio, 2024. Disponível em: [https://pragmaticstudio.com/courses/phoenix](https://pragmaticstudio.com/courses/phoenix). Acesso em: 04 nov. 2024.

PRAGMATIC STUDIO. LiveView LifeCycle. In: **Phoenix LiveView Programming**. Pragmatic Studio, 2024. Disponível em: [https://pragmaticstudio.com/courses/phoenix](https://pragmaticstudio.com/courses/phoenix). Acesso em: 26 nov. 2024.

PHOENIX. LiveView. _Phoenix LiveView Documentation_. Disponível em: [https://hexdocs.pm/phoenix_live_view/Phoenix.LiveView.html](https://hexdocs.pm/phoenix_live_view/Phoenix.LiveView.html). Acesso em: 19 nov. 2024.
