---
Criado: 2024-11-06T21:58
Atualizado: 2025-05-23T14:09
Estudado: 2025-08-06T11:36
Links:
  - "[[Elixir language]]"
  - "[[Função anônima]]"
  - "[[Closure]]"
---
---
# Elixir - Função anônima

Em Elixir, elas não tem nome mas podem ser atribuídas a variáveis. São chamadas com o operador `.( )` após avariável que a contém. Elas também podem capturar variáveis do contexto onde foram criadas (closure).

Podem ser definidas de duas maneiras:

- usando a sintaxe com `fn` e `end`

```elixir
# Função anônima que recebe um número e retorna o seu quadrado
square = fn x -> x * x end
IO.puts(square.(4)) # Saída: 16
```

- usando a sintaxe com o operador `&`

```elixir
# Função anônima com o que recebe x e retorna x * 2
double = &(&1 * 2)
IO.puts(double.(4)) # Saída: 8
```

---

## References

ELIXIR: Anonymous functions. Disponível em: https://hexdocs.pm/elixir/anonymous-functions.html. Acesso em: 06 de novembro  de 2024.