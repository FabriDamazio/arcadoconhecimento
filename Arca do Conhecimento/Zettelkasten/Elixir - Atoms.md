---
Criado: 2025-11-17T15:10
Atualizado: 2025-11-17T15:10
Estudado: 2025-11-17T15:10
Links:
  - "[[Elixir - Tipos de dados]]"
tags:
  - elixir
  - programação
---
---
# Elixir - Atoms

Atoms são constantes cujo seu valor é seu próprio nome.

```elixir
iex> :apple 
:apple
iex> :orange
:orange
iex> :apple == :apple
true
iex> :apple == :orange
false
```

Para os atoms os seguintes atoms abaixo, não é necessário o uso dos `:` antes de seu nome:

```elixir
true
false
nil
```

Atoms devem ser compostos por characters Unicode como letras, números, underscore e @. Ele pode ter espaços quando dentro de aspas:

```elixir
iex> :"este atom tem espaco"
:"este atom tem espaco"
```


---
## References

ELIXIR. Atom. Documentação do Elixir v1.19.3, 2025. Disponível em: https://hexdocs.pm/elixir/1.12/Atom.html. Acesso em: 17 nov. 2025.