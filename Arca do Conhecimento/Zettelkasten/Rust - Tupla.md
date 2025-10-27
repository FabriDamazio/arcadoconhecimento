---
Criado: 2025-06-05T20:56
Atualizado: 2025-06-05T20:56
Estudado: 2025-07-30T15:32
Links:
  - "[[Rust - Tipos de dados]]"
tags:
  - rust
  - programação
---
---
# Rust - Tupla

Uma tupla, de maneira geral, é utilizada para agrupar dados de tipos diferentes em um único tipo composto.

```rust
// Criando uma tupla
let tup: (i32, f64, u8) = (500, 6.4, 1);

// Decompondo uma usando pattern matching
let (x, y, z) = tup;

// Acessando o valor de uma tupla pelo index
let x = tup.0;
let y = tup.1;
let z = tup.2; 
```

Uma tupla sem nenhum valor é conhecido como o tipo primitivo unit.

---
## References

KLABNIK, Steve; NICHOLSON, Carol. _Data Types_. In: _The Rust Programming Language_. Disponível em: [https://rust-book.cs.brown.edu/ch03-02-data-types.html](https://rust-book.cs.brown.edu/ch03-02-data-types.html). Acesso em: 5 jun. 2025.