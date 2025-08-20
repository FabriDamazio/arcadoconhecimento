---
Criado: 2025-01-02T09:06
Atualizado: 2025-05-23T14:09
Estudado: 2025-08-20T11:50:00
Links:
  - "[[Metaprogramming em Elixir]]"
---
---
# Elixir - AST  (Abstract Syntax Tree)

No Elixir, a Abstract Syntax Tree (que também pode ser conhecida como uma quoted expression) é a maneira da linguagem de representar um código como dados no formato de uma árvore.

Cada nó da AST é formada por uma tupla de 3 elementos onde:
- O primeiro é um atom que representa a operação.
- O segundo é uma keyword list com metadados.
- O terceiro é a lista de argumentos da operação (que pode inclusive ter outros nós).

```elixir
# Um nó da AST que representa a operação 2 + 3
{:+, [], [2, 3]}

# Uma variável primeiro elemento é seu nome, o segundo metadados e o terceiro o seu contexto
{:foo, [], BarModule}
```

Para transformar um código Elixir em AST, deve-se usar a função `quote/2` e de AST para código a função `unquote/1` do módulo `Kernel`.

---
## References

**DORGAN, Paul.** _The Elixir AST._ 20 abr. 2021. Disponível em: [https://dorgan.ar/posts/2021/04/the_elixir_ast/](https://dorgan.ar/posts/2021/04/the_elixir_ast/). Acesso em: 22 dez. 2024.

**ELIXIR.** _The Elixir AST._ Syntax Reference, versão 1.13.4. Disponível em: [https://hexdocs.pm/elixir/1.13.4/syntax-reference.html#the-elixir-ast](https://hexdocs.pm/elixir/1.13.4/syntax-reference.html#the-elixir-ast). Acesso em: 22 dez. 2024.