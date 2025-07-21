---
Criado: 2024-12-04T19:38
Atualizado: 2025-05-23T13:10
Estudado: 2025-07-18T11:01
Links:
  - "[[Phoenix Component]]"
---
---
# Atributos do Phoenix Component

Cada componente pode ter diferentes atributos que são dados que podem ser passados em seu `Map` de assigns. O módulo `Phoenix.Component`possui a macro `attr/3` para que seja possível declara-los logo antes da função do componente.

```elixir
attr :name, :string, required: true

def greet(assigns) do
  ~H"""
  <p>Hello, {@name}!</p>
  """
end
```

Nesta macro é possível declarar o nome do atributo, seu tipo e algumas opções como valor padrão, valores aceitos, se é obrigatório, etc.

Os atributos são validados apenas em **tempo de compilação**.

Um maior detalhamento se encontra na documentação oficial nos links de referência.

---

## References

PHOENIX Framework. _Phoenix.Component_. Disponível em: [https://hexdocs.pm/phoenix_live_view/Phoenix.Component.html](https://hexdocs.pm/phoenix_live_view/Phoenix.Component.html). Acesso em: 4 dez. 2024.

PHOENIX Framework. _Phoenix.Component — Macro attr/3_. Disponível em: [https://hexdocs.pm/phoenix_live_view/Phoenix.Component.html#attr/3](https://hexdocs.pm/phoenix_live_view/Phoenix.Component.html#attr/3). Acesso em: 4 dez. 2024.---
