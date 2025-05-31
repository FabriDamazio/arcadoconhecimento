---
Criado: 2024-11-08T10:43
Atualizado: 2025-05-23T14:13
Estudado: 2025-05-31T13:43
Links:
  - "[[Elixir language]]"
---
---
# Elixir - Guards

Guards é uma maneira de complementar o pattern matching com verificações mais complexas. Pode ser utilizado nas cláusulas (clauses) de funções, funções anônimas, for, with e case. No `try` é possível utilizar guards no `catch` e no `else`. O `receive` também suporta o uso de guards para receber mensagens.


- Guards começão com a keyword `when`.
- Por convenção, os nomes das guards começão com o prefixo `_is`
- Guard expressions são funções que devem ser puras e não realizar mutação de nenhum estado global e devem retornar `true` ou `false`.
- Existe uma lista de guards comum na [documentação do Elixir](https://hexdocs.pm/elixir/Kernel.html#guards), entre elas `is_integer/1`, `is_list/1` , `is_nil` e muitas outras.

Exemplo do uso em função:

```elixir
def empty?(list) when is_list(list) and length(list) == 0, do: true
```

Exemplo em case:

```elixir
case x do
	x when is_integer(x) -> x
	_ -> :not_an_integer
end
```

Exemplo em função anônima:

```elixir
larger_than_two? = fn
  n when is_integer(n) and n > 2 -> true
  n when is_integer(n) -> false
end
```

Exemplo de uso em `for`:

```elixir
for x when x >= 0 <- [1, -2, 3, -4], do: x
```

É possível criar sua própria definição de uma guard utilizando `defguard`:

```elixir
defmodule HTTP do 
	# definição da guard
	defguard is_success(code) when code >= 200 and code < 300 

	# uso da guard
	def handle_response(code) when is_success(code) do :ok end 
end

```


---

## References

ELIXIR. _Guards_. Disponível em: [https://hexdocs.pm/elixir/patterns-and-guards.html#guards](https://hexdocs.pm/elixir/patterns-and-guards.html#guards). Acesso em: 8 nov. 2024.