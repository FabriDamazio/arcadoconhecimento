---
Criado: 2024-11-02T21:05
Atualizado: 2025-06-19T11:15
Estudado: 2025-07-09T10:42
Links:
  - "[[Elixir language]]"
---
---
# Elixir - Tipos de dados

Os tipos básicos em Elixir são:

- **Integer**: Números inteiros (`42`, `0x1F` para hexadecimal)
- **Float**: Números decimais (`3.14`, `-0.5`)
- **Boolean**: Valores lógicos (`true`, `false` – que são atoms especiais)
- **Atom**: Constantes nomeadas (`:ok`, `:error`)
- **String**: Texto UTF-8 entre aspas duplas (`"Elixir"`)
- **Char**: Código Unicode de um caractere (`?A` equivale a `65`)

Os principais tipos compostos são:

- **List**: Coleções ordenadas (`[1, 2, 3]`, `['a', 'b']`).
- **Tuple**: Estruturas fixas e imutáveis (`{:ok, 42}`, `{1, 2, 3}`).
- **Map**: Dicionários chave-valor (`%{name: "Ana", age: 30}`).
- **Struct**: Mapas com esquema definido (`%User{name: "Ana"}`).
- **Charlist**: Listas de inteiros representando caracteres (`'abc'`).

Para trabalhar com dados binários:

- **Binary**: Sequência de bytes (múltiplos de 8 bits), como `<<65, 66>>`.
- **Bitstring**: Sequência de bits de tamanho arbitrário (`<<1::1, 0::1>>`).
    
Incluem utilitários e tipos para cenários específicos:

- **Regex**: Expressões regulares (`~r/foo/`).
- **Data e Hora**:
    - `~D[2024-01-01]` (data),
    - `~T[14:30:00]` (horário),
    - `~U[2024-01-01 14:30:00Z]` (data/hora com fuso UTC).
- **PID**: Identificador de processo (`#PID<0.123.0>`).
- **Function**: Funções anônimas (`fn x -> x * 2 end`).

``` elixir
# ====================
# TIPOS BÁSICOS
# ====================
42           # integer
-1           # integer
0xFF         # integer (hexadecimal)
0o777        # integer (octal)
0b1010       # integer (binário)
3.14         # float
-0.5         # float
true         # boolean
false        # boolean
:ok          # atom
:error       # atom
nil          # nil (atom especial)
"Elixir"     # string (binário UTF-8)
?A           # char (inteiro Unicode)

# ====================
# TIPOS COMPOSTOS
# ====================
[1, 2, 3]    # list
[]           # lista vazia
{:ok, 42}    # tuple
{}           # tupla vazia
%{a: 1, b: 2} # map
%User{name: "Ana"} # struct (map com esquema definido)
'abc'        # charlist (lista de inteiros Unicode)

# ====================
# TIPOS BINÁRIOS
# ====================
<<1, 2>>     # binary (sequência de bytes)
<<1::1, 0::1>> # bitstring (sequência de bits arbitrária)

# ====================
# TIPOS ESPECIAIS/DE DATA
# ====================
~r/foo/      # regex (expressão regular)
~D[2024-01-01] # date (data)
~T[14:30:00] # time (horário)
~U[2024-01-01 14:30:00Z] # datetime (data e hora com fuso UTC)
~N[2024-01-01 14:30:00] # naive datetime (data e hora sem fuso)
```



---

## References

HEXDOCS PM. _Elixir Basic Types_. Disponível em: [https://hexdocs.pm/elixir/basic-types.html](https://hexdocs.pm/elixir/basic-types.html). Acesso em: 2 nov. 2024.