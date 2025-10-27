---
Criado: 2025-08-26T14:47
Atualizado: 2025-08-26T14:47
Estudado: 2025-08-26T14:47
Links:
  - "[[Rust language]]"
  - "[[Rust - Bit Shifting]]"
tags:
  - rust
  - programação
---
---
# Rust - Operações Bitwise (bit a bit)

Rust fornece um conjunto completo de operadores bitwise para manipulação direta de bits, essenciais para programação de sistemas e otimizações de baixo nível.

**Operadores disponíveis:**

 ```rust
// Definindo dois números binários
let a = 0b1100; // 12 em decimal
let b = 0b1010; // 10 em decimal

// AND bitwise
let and_result = a & b;  // 0b1000 (8)

// OR bitwise  
let or_result = a | b;   // 0b1110 (14)

// XOR bitwise
let xor_result = a ^ b;  // 0b0110 (6)

// NOT bitwise (inversão)
let not_result = !a;     // 0b1111...0011 (complemento de 2)

// Shift left
let shift_left = a << 2; // 0b110000 (48)

// Shift right
let shift_right = a >> 1; // 0b0110 (6)
 ```

## Operadores de atribuição composta

Os operadores de atribuição composta combinam uma operação bitwise com uma atribuição, tornando o código mais conciso e evitando a repetição do nome da variável. Os operadores de atribuição composta têm **baixa precedência** e são avaliados da **direita para a esquerda**.

**Operadores disponíveis:**

| Operador | Equivalente  | Descrição                  |
| -------- | ------------ | -------------------------- |
| `&=`     | `a = a & b`  | AND bitwise com atribuição |
| `\|=`    | `a = a \| b` | OR bitwise com atribuição  |
| `^=`     | `a = a ^ b`  | XOR bitwise com atribuição |
| `<<=`    | `a = a << b` | Shift left com atribuição  |
| `>>=`    | `a = a >> b` | Shift right com atribuição |
Para mais informações sobre o funcionamento de operadores de shift, acesse [[Rust - Bit Shifting]].

---
## References

**RUST**. **Appendix A - Operators and Symbols**. In: **The Rust Programming Language**. S. l., 2023. Disponível em: [https://doc.rust-lang.org/book/appendix-02-operators.html](https://doc.rust-lang.org/book/appendix-02-operators.html). Acesso em: 28 ago. 2023.