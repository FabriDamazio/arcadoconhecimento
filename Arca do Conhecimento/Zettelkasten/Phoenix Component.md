2024-12-04 - 10:38
Tags: [[Phoenix Framework]] [[Atributos do Phoenix Component ]] [[Phoenix Components Slots]]

# Phoenix Component

São components reutilizáveis para criar interfaces modulares. O componente é uma função que recebe um `Map` de assigns como argumento e retorna uma struct `Phoenix.LiveView.Rendered` construída com o sigil `~H`.

Exemplo de um componente:

```elixir
defmodule RaffleyWeb.CustomComponents do
  use Phoenix.Component

  attr :status, :atom, required: true, values: [:upcoming, :open, :close]
  attr :class, :string, default: nil

  def badge(assigns) do
    ~H"""
    <div class={[
      "rounded-md px-2 py-1 text-xs font-medium uppercase inline-block border",
      @status == :open && "text-lime-600 border-lime-600",
      @status == :upcoming && "text-amber-600 border-amber-600",
      @status == :closed && "text-gray-600 border-gray-600",
      @class
    ]}>
      <%= @status %>
    </div>
    """
  end
end
```

É possível definir atributos ao componente, especificando seu nome, tipo, valor padrão e outras opções

---

# References

PHOENIX Framework. _Phoenix.Component_. Disponível em: [https://hexdocs.pm/phoenix_live_view/Phoenix.Component.html](https://hexdocs.pm/phoenix_live_view/Phoenix.Component.html). Acesso em: 4 dez. 2024.