---
Criado: 2025-01-03T09:20
Atualizado: 2025-05-23T16:29
Estudado: 2025-07-02T10:49
Links:
  - "[[Elixir Data Structures]]"
---
---
# Elixir - Map

Map é uma estrutura de dados associativa que armazena informações em pares de chave-valor. As chaves e valores podem ser de qualquer tipo. Caso a chave seja um atom, é possível acessar seu valor utilizando dot syntax.

```elixir
# criando um Map vazio
%{}

# sintaxe para chave do tipo atom (usando :)
%{chave: 1}

# sintaxe para chaves de outros tipos (usando =>)
%{1 => :test, "2" => "dois", atom_key: 3}

# acessando o valor de uma chave do tipo atom (dot syntax)
x = %{1 => :test, "2" => "dois", atom_key: 3}
x.atom_key

# acessando o valor de uma chave do tipo diferente de atom
x = %{1 => :test, "2" => "dois", atom_key: 3}
x[1]
```

Pattern Matching:

```elixir

# variáveis podem ser usadas como chave
iex> x = "test"
"test"

iex> %{x => 1}
%{"test" => 1}

# e também no patten matching
iex> %{a: a} = %{:a => 1}
iex> a
1 

```

Sintaxe específica para atualização de maps:

```elixir
# atualizando o valor de uma chave EXISTENTE
# se a chave não existir, é lançado um KeyError
iex> map = %{one: 1, two: 2}
iex> %{map | two: 3}
%{one: 1, two: 3}
```


---
## References

**ELIXIR.** _Keywords and maps._ HexDocs. Disponível em: [https://hexdocs.pm/elixir/keywords-and-maps.html](https://hexdocs.pm/elixir/keywords-and-maps.html). Acesso em: 03 jan 2025.

**ELIXIR.** _Map._ Documentação oficial, versão 1.18.1. Disponível em: [https://hexdocs.pm/elixir/1.18.1/Map.html](https://hexdocs.pm/elixir/1.18.1/Map.html). Acesso em: 05 jan. 2025.