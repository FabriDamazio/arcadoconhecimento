---
Criado: 2024-12-06T09:21
Atualizado: 2025-05-23T16:57
Estudado: 2025-08-20T11:47:00
Links:
  - "[[Phoenix Component]]"
tags:
  - elixir
  - programação
---
---
# Phoenix Components Slots

Além de atributos, os componentes podem receber blocos com conteúdo no formato HEEx. Estes blocos são chamados de slots e podem ser passados utilizando a macro `slot/3`.

Exemplo de um component que aceita o slot padrão (chamado inner_block):

```elixir
slot :inner_block, required: true
  
def banner(assigns) do
  ~H"""
  <div class="banner">
    <h1>
      <%= render_slot(@inner_block) %>
    </h1>
  </div>
  """
end

```

O componente pode receber diversos slots se preciso. No exemplo abaixo temos o slot padrão inner_block e o slot details. Diferentemente do slot padrão, os outros slots são dinâmicos, ou seja, o slot details é uma lista de slots do tipo details:

```elixir
# Declarando o componente
slot :inner_block, required: true
slot :details

def banner(assigns) do
  ~H"""
  <div class="banner">
    <h1>
	  <%= render_slot(@inner_block) %>
    </h1>
    <div :for={details <- @details} class="details">
	  <%= render_slot(details) %>
    </div>
  </div>
  """
end

# Utilizando o componente
<.banner>
  <.icon name="hero-sparkles-solid" /> Mistery Raffle Coming Soon!
  <:details>
    To Be Revelead Tomorrow
  </:details>
  <:details>
    Any guesses?
  </:details>
</.banner>
```

Um slot pode receber atributos. No exemplo abaixo, uma nova chave chamada `:emoji` é adicionada ao `Map` de assigns. Depois ela é passada para a função `render_slot` dos slots de `details` para que possa ser capturada no seu atributo `:let`:

```elixir
# Declarando o componente e passando :emoji para o slot
slot :inner_block, required: true
slot :details

def banner(assigns) do
  assigns = assign(assigns, :emoji, ~w(😎 🤩 🥳) |> Enum.random())

  ~H"""
  <div class="banner">
    <h1>
	  <%= render_slot(@inner_block) %>
    </h1>
    <div :for={details <- @details} class="details">
	  <%= render_slot(details, @emoji) %>
    </div>
  </div>
  """
end

# Utilizando o componente e capturando o emoji no atributo :let
<.banner>
  <.icon name="hero-sparkles-solid" /> Mistery Raffle Coming Soon!
  <:details :let={vibe}>
    To Be Revelead Tomorrow <%= vibe %>
  </:details>
  <:details>
    Any guesses?
  </:details>
</.banner>
```


---
## References

PHOENIX Framework. _Phoenix.Component_. Disponível em: https://hexdocs.pm/phoenix_live_view/Phoenix.Component.html#module-slots. Acesso em: 6 dez. 2024.