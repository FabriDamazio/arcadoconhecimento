---
Criado: 2025-11-25T08:45
Atualizado: 2025-11-25T08:45
Estudado: 2025-11-25T08:45
Links:
  - "[[Elixir - Tipos de dados]]"
tags:
  - elixir
  - programação
---
# Strings

É uma sequência de caracteres Unicode, tipicamente escritos entre aspas duplas.

```elixir
# criando uma string
"elixir"
texto = "elixir"

# string com escape characters
texto = "Linha1\nLinha2\nLinha3"
# output:
# Linha1
# Linha2
# Linha3

citacao = "ele disse \"oi\"."
# output: ele disse "oi".

# string usando quebra de linha
poema = " rosas são vermelhas
violetas são azuis"
#output:
# rosas são vermelhas
# violetas são azuis

```

## Concatenação de strings

Strings podem ser concatenas utilizando o operador `<>` do módulo `Kernel`. Ele é um operador de concatenação de dois binários.

```elixir
"hello" <> "world"
#=> "hello world"
```

## Interpolação de strings

Strings suportam interpolação. Um valor pode ser colocado no meio de uma string usando a sintaxe `#{}`. Além disso, qualquer expressão válida de Elixir também pode ser interpolada desde que o valor para qual ela é avaliada possa ser convertida para uma string (caso não possa ser convertido, um protocol error acontece).

```elixir
# interpolando um valor
nome = "João"
texto = "olá #{nome}"
#=> olá João

# interpolando uma expressão
resultado = "O resultado é: #{2 + 2}"
#=> O resultado é: 4
```

---
## References

ELIXIR. **String**. In: __HexDocs__: Elixir documentation. Disponível em: https://hexdocs.pm/elixir/String.html. Acesso em: 25 nov. 2025.