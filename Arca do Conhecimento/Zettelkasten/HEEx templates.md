---
Criado: 2024-11-14T15:37
Atualizado: 2025-05-23T16:42
Estudado: 2025-06-26T09:50
Links:
  - "[[Phoenix Framework]]"
  - "[[EEx]]"
---
---
# HEEx templates

A linguagem de template do Phoenix é chamada HEEx (HTML + EEx). Os templates podem ser criados como arquivos com a extensão `.heex` ou diretamente através do sigil `~H`.

Estes templates possuem algumas vantagens dos templates EEx, como:

- escape automático das expressões dinâmicas `<%= %>`, gerando sempre HTML seguro.
- validação do HTML estático do template.
- criação de componentes e slots.

Os templates HEEx podem ser usados tanto em páginas tradicionais como o LiveView.

As funções `Phoenix.Component.assign/2` e `Phoenix.Component.assign/3` ajudam a armazenar  valores. Esses valores podem ser acessados no LiveView como `socket.assigns.name`, mas dentro dos templates HEEx, são acessados como `@name`.

```elixir
# usando assign no liveview
assign(socket, :users, Repo.all(User))

# acessando o valor no template
<%= for user <- @users do %>
  <%= user.name %>
<% end %>
```

---
## References

PHOENIX COMPONENTS. Disponível em: [https://hexdocs.pm/phoenix/components.html](https://hexdocs.pm/phoenix/components.html). Acesso em: 14 nov. 2024.

PHOENIX LIVE VIEW - Assigns in EEx templates. Disponível em: [https://hexdocs.pm/phoenix_live_view/assigns-eex.html](https://hexdocs.pm/phoenix_live_view/assigns-eex.html). Acesso em: 14 nov. 2024.