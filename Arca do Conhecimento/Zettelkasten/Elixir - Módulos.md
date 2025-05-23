---
Criado: 2025-01-08T10:50
Atualizado: 2025-05-23T16:30
Estudado: 2025-01-08T10:50
Links:
  - "[[Elixir language]]"
---
---
# Elixir - Módulos

Os módulos permitem a organização e agrupamento de funções em um namespace.

Definindo e usando um módulo:

```elixir
defmodule Example do
  def hello(name) do
    "Hello #{name}"
  end
end

iex> Example.hello("Fabri")
"Hello Fabri"
```

A definição de um módulo pode ser aninhada, ou seja, um módulo pode ser definido dentro do outro ou utilizando namespace como `Example.Nested2`.

## Atributos (module attributes)

É possível declarar atributos a um módulo. São, de forma geral, usados como constantes. Exemplo:

```elixir
defmodule Example do
  # declaração de um atributo (nome e valor)
  @greeting "Hello"

  def hello(name) do
    "#{@greeting} #{name}"
  end
end
```

Existem alguns nomes de atributos que são reservados, como `@doc` para documentar uma função ou macro, `@moduledoc` para documentar o módulo, `@behaviour` e entre outros.

## Declaração de structs

As structs devem ser declaradas dentro de um módulo.

---

## References

**ELIXIR SCHOOL.** _Módulos._ Disponível em: [https://elixirschool.com/pt/lessons/basics/modules](https://elixirschool.com/pt/lessons/basics/modules). Acesso em: 8 jan. 2025.