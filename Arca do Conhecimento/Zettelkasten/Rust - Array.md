---
Criado: 2025-06-05T21:11
Atualizado: 2025-06-05T21:11
Estudado: 2025-07-30T15:34
Links:
  - "[[Rust - Tipos de dados]]"
tags:
  - rust
  - programação
---
---
# Rust - Array

É uma coleção de elementos de tamanho fixo e com todos elementos do mesmo tipo e alocada na stack. São especialmente úteis quando sabemos seu número de elementos e eles não precisam ser alterados.

```rust
let months = ["January", "February", "March", "April", "May", "June", "July",
              "August", "September", "October", "November", "December"];

let a: [i32; 5] = [1, 2, 3, 4, 5];

// É possível iniciar uma array com todos elementos com um valor inicial
let a = [3; 5]; // equivalente a let a = [3, 3, 3, 3, 3];

// Acessando utilizando o index
let first = a[0];

// Caso tente acessar um index inexistente temos um runtime error.
```


---
## References

KLABNIK, Steve; NICHOLSON, Carol. _Data Types_. In: _The Rust Programming Language_. Disponível em: [https://rust-book.cs.brown.edu/ch03-02-data-types.html](https://rust-book.cs.brown.edu/ch03-02-data-types.html). Acesso em: 5 jun. 2025.