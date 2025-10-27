---
Criado: 2025-07-22T18:18
Atualizado: 2025-07-22T18:18
Estudado: 2025-08-20T12:00:00
Links:
  - "[[Elixir - Tipos de dados]]"
tags:
  - programação
  - elixir
---
---
# Bitstring

É um tipo de dado primário em Elixir. É uma sequência contígua de bits de tamanho arbitrário. Se ela tem o tamanho múltiplo de 8 bits (ex: 8, 16, 24 bits), ela é chamada de **binary**, que é um subtipo ou caso especial de *bitstring*.

Bitstrings são definidas utilizando a notação `<<>>`. Ela é definida em segmentos e cada segmento tem um tipo e um valor separados por `::`. O tipo especifica quantos bits serão usados para o codificar (encode) o valor. Se o tipo não foi informado ele terá o valor padrão de 8 bits.

## Binary

Um binário (binary) é o nome de uma bitstring que tem seu tamanho de  valor padrão dividido por 8.

```elixir
# criando uma bitstring com tamanho padrão 8 bits
<<42>>

# criando uma bitstring especificando o padrão
<<42::8>>
<<3::4>>

# verificando se a bitstring é um binário
is_bitstring(<<42>>) # => true
is_bitstring(<<3::4>>) # => true
is_binary(<<42>>) # => true
is_binary(<<3::4>>) # => false - não é divisível por 8

# pattern matching
<<0, 1, x>> = <<0, 1, 2>> # x é igual a 2
<<0, 1, x::binary>> = <<0, 1, 2, 3>> # x é <<2,3>>
<<head::binary-size(2), rest::binary>> = <<0, 1, 2, 3>> # head é <<0, 1>> e rest <<2, 3>>
```


## Strings são binários

String são binários codificados e UTF-8 (UTF-8 encodade binary) onde cada um dos caracteres são codificados usando de 1 a 4 bytes. Toda string é um binário mas, devido as regras padrões do UTF-8, nem todo binário é uma string válida.

```elixir
is_binary("hello") # => true
is_binary(<<239, 191, 19>>) # => true
String.valid?(<<239, 191, 19>>) # => false
```

Uma concatenação de string é uma concatenação de binários

```elixir
"a" <> "ha" # => "aha"
<<0, 1>> <> <<2, 3>> # => <<0, 1, 2, 3>>
```

---
## References

**ELIXIR.** Binaries, strings, and charlists. **HexDocs**, 2023. Disponível em: [https://hexdocs.pm/elixir/binaries-strings-and-charlists.html#bitstrings](https://hexdocs.pm/elixir/binaries-strings-and-charlists.html#bitstrings). Acesso em: 24 jul. 2025.