---
Criado: 2025-08-25T14:53
Atualizado: 2025-08-25T14:53
Estudado: 2025-08-25T14:53
Links:
  - "[[Elixir language]]"
---
---
Operações bitwise (bit a bit) em Elixir são implementadas via módulo `Bitwise`, que possui uma conjunto de funções para fazer cálculos em bits. Ela funciona apenas em `integers`.

**Operadores disponíveis:**

```elixir
x = 0b1100 # => 12
y = 0b1010 # => 10

# AND bitwise
x &&& y 
Bitwise.band(x, y)
# => 1000 em binário ou 8 em decimal

# OR bitwise
x ||| y 
Bitwise.bor(x,y)
#=> 1110 em binário ou 14 em decimal

# XOR bitwise
Bitwise.bxor(x,y)
# => 0110 em binário ou 6 em decimal

# NOT bitwise (inversão)
~~~x
Bitwise.bnot(x)
# => 1111...0011 (complemento de 2)

# Shift left
x <<< 1 
Bitwise.bsl(x, 1)
# => 11000 em binário ou 24 em decimal

# Shift right
x >>> 1
Bitwise.bsr(x, 1)
# => 0110 em binário ou 6 em decimal
```

No elixir não existem operadores bitwise compostos.

---
## References

**ELIXIR**. **Bitwise**. HexDocs, S. l., 2023. Disponível em: [https://hexdocs.pm/elixir/Bitwise.html](https://hexdocs.pm/elixir/Bitwise.html). Acesso em: 28 ago. 2025.