---
Criado: 2025-10-27T19:23
Atualizado: 2025-10-29T19:23:00
Estudado: 2025-10-29T19:23:00
Links:
  - "[[Elixir - Tipos de dados]]"
tags:
  - elixir
---
---
# Elixir - Integer e Floats

##  Representação de integer e floats 

```elixir
255       # inteiro
0xFF      # inteiro em hexadecimal
0o377     # inteiro em octal
0b1010    # inteiro em binário
255_000   # inteiro com separador de milhar (equivale a 255000)
-255      # inteiro negativo
?a        # codepoint Unicode (97)

3.14      # float
-3.14     # float negativo
1.0e-10   # notação cientifica

```

## Operações aritméticas básicas

```elixir
# Integers
5 + 5  # 10
6 / 2  # 3.0 (sempre retorna float)
5 * 2  # 10

div(5, 2) # 2 (retorna o inteiro)
rem(5, 2) # 1 (resto)

# floats
5.0 + 2.0  # 7.0
6.0 / 2.0  # 3.0 (retorna float)
6.0 * 2.0  # 12.0 (float)
```

## Conversão entre tipos

```elixir
# string para número
String.to_integer("123")  # 123
String.to_float("3.14")   # 3.14

# numero para string
Integer.to_string(123)    # "123"
Float.to_string(3.14)     # "3.14"


```

## Comparações

```elixir
# integer vs integer
1 = 1   # 1
1 == 1  # true
1 === 1 # true
1 < 2   # true

# float vs float
1.0 = 1.0    # 1.0
1.0 == 1.0   # true
1.0 === 1.0  # true
1.0 < 2.0    # true

# integer vs float
1 = 1.0   # MatchError
1 == 1.0  # true
1 === 1.0 # false (comparação estrita de tipo)
1 < 2.0   # true
```

## Informações importantes

- **Integer tem precisão arbitrária**, isso significa que o tamanho do inteiro não tem limite (sendo a memória disponível no sistema este limite). Outras linguagens geralmente tem inteiros com tamanhos fixos como 32 ou 64 bits.
- **Sem overflow** para inteiros por não possuir um tamanho fixo.
- **Float são representados por 64 bits** seguindo o padrão IEEE 754.
- **Não use float para cálculos monetários**. Bibliotecas específicas são recomendadas.

```elixir
# Divisão por zero
# 1 / 0   # ** (ArithmeticError) bad argument in arithmetic expression

# Float com precisão limitada
0.1 + 0.2 # 0.30000000000000004 (comportamento padrão IEEE 754)
```

---
## References

ELIXIR. Basic types. Hexdocs, 2024. Disponível em: https://hexdocs.pm/elixir/basic-types.html. Acesso em: 27 de outubro de 2025.