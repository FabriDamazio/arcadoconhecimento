2025-01-03 - 09:20
Status: #idea
Tags: [[Elixir - Map data structure]]

# Elixir - Map

Map é uma estrutura de dados associativa que armazena informações em pares de chave-valor. As chaves e valores podem ser de qualquer tipo. Caso a chave seja um atom, é possível acessar seu valor utilizando dot syntax.

```elixir
# criando um Map vazio
%{}

# um Map com chave do tipo atom
%{chave: 1}

# um Map com chaves de outros tipos
%{1 => :test, "2" => "dois", atom_key: 3}

# acessando o valor de uma chave do tipo atom com dot syntax
x = %{1 => :test, "2" => "dois", atom_key: 3}
x.atom_key

# acessando o valor de uma chave do tipo diferente de atom
x = %{1 => :test, "2" => "dois", atom_key: 3}
x[1]
```



---

# References

**ELIXIR.** _Keywords and maps._ HexDocs. Disponível em: [https://hexdocs.pm/elixir/keywords-and-maps.html](https://hexdocs.pm/elixir/keywords-and-maps.html). Acesso em: 22 dez. 2024.