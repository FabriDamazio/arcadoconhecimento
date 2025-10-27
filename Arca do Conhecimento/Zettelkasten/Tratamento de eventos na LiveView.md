---
Criado: 2024-11-28T20:23
Atualizado: 2025-05-23T17:29
Estudado: 2025-08-20T11:46:00
Links:
  - "[[Phoenix LiveView]]"
tags:
  - elixir
  - programação
---
---
# Tratamento de eventos na LiveView

LiveView é um processo que recebe eventos, atualiza seu estado conforme necessário, renderiza um template e envia de volta os diffs.

Os eventos podem ser enviados externamente pelo navegador, sendo tratados em callbacks `handle_event`:

```elixir
def handle_event(event, params, socket) do
  # trata o evento

  {:noreply, socket}
end
```

Os eventos também podem ser enviados internamente pelo próprio LiveView (ou por qualquer outro processo Elixir) como mensagens, sendo tratados em callbacks `handle_info`:


```elixir
def handle_info(message, socket) do
  # trata a mensagem

  {:noreply, socket}
end
```

Já para `call` e `cast` enviados por um GenServer, são usados os callbacks `handle_call` e `handle_cast`.


---
## References

PRAGMATIC STUDIO. Handling Process Messages. In: **Phoenix LiveView Programming**. Pragmatic Studio, 2024. Disponível em: [https://pragmaticstudio.com/courses/phoenix](https://pragmaticstudio.com/courses/phoenix). Acesso em: 28 nov. 2024.

PHOENIX. LiveView. _Phoenix LiveView Documentation_. Disponível em: [https://hexdocs.pm/phoenix_live_view/Phoenix.LiveView.html#callbacks](https://hexdocs.pm/phoenix_live_view/Phoenix.LiveView.html#callbacks). Acesso em: 28 nov. 2024.