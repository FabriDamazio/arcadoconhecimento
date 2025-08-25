---
Criado: 2025-08-23T09:56
Atualizado: 2025-08-23T09:56
Estudado: 2025-08-23T09:56
Links:
  - "[[Rust language]]"
---
---
# Rust - Bit Shifting

Operações de shift (deslocamento) são operadores que movem os bits de um número inteiro para a esquerda ou direita. Em Rust, existem dois tipos principais:

### Shift Left (<<)
Desloca os bits para a esquerda, preenchendo com zeros à direita:
```rust
let x = 5; // 101 em binário = 5 em decimal
let y = x << 1; // 1010 em binário = 10 em decimal
```

### Shift Right (>>)
Desloca os bits para a direita. Com inteiros sem sinal (u8, u16, etc.), preenche com zeros à esquerda.  Com inteiros com sinal (i8, i16, etc.), replica o bit de sinal (arithmetic shift):
```rust
let x = 10; // 1010 em binário = 10 em decimal
let y = x >> 1; // 0101 em binário = 5 em decimal

let a = -10; // -1010 em binário = -10 em decimal
let b = a >> 1; // -0101 em binário = -5 em decimal
```

## Uso Prático

### Verificação de Paridade

```rust
fn is_even(n: i32) -> bool {
    (n & 1) == 0 // Verifica se o bit menos significativo é 0
}
```

### Multiplicação e Divisão por Potências de 2

```rust
let x = 8;
let double = x << 1;  // x * 2
let half = x >> 1;    // x / 2
```

### Manipulação de Flags

```rust
const READ: u32 = 1 << 0;   // 1
const WRITE: u32 = 1 << 1;  // 2
const EXECUTE: u32 = 1 << 2; // 4

let permissions = READ | WRITE; // 3
let has_read = permissions & READ != 0; // true
```

## Importante

- Shifts são mais rápidos que operações de multiplicação/divisão em potências de 2, porém compiladores modernos (como o rustc) já otimizam automaticamente `x * 2` para `x << 1`. 
- Não há overflow em tempo de execução (em operações padrão), mas os bits fora do tipo são truncados.
- Para números negativos, o comportamento é definido para shift right aritmético (preserva o sinal).
- Em Rust, os tipos de shift devem ser compatíveis com o tipo do valor.

---
## References

THE RUST REFERENCE. **Arithmetic and Logical Binary Operators**. 2025. Disponível em: [https://doc.rust-lang.org/reference/expressions/operator-expr.html#arithmetic-and-logical-binary-operators](https://doc.rust-lang.org/reference/expressions/operator-expr.html#arithmetic-and-logical-binary-operators). Acesso em: 25 aug. 2025.