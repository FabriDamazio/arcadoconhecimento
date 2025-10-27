---
Criado: 2025-06-02T14:41
Atualizado: 2025-06-02T14:41
Estudado: 2025-08-13T16:25
Links:
  - "[[Rust - Tipos de dados]]"
tags:
  - rust
  - programação
---
---
# Rust - Character type

É o tipo alfabético mais primitivo. Tem 4 bytes em tamanho e pode representar ASCII, caracteres com acento, Chinês, Japonês, Coreano, Emoji.

```rust
let c = 'z'; // tipo implícito
let z: char = 'ℤ'; // tipo explícito
let heart_eyed_cat = '😻';
```

---
## References

KLABNIK, Steve; NICHOLSON, Carol. _Data Types_. In: _The Rust Programming Language_. Disponível em: [https://rust-book.cs.brown.edu/ch03-02-data-types.html](https://rust-book.cs.brown.edu/ch03-02-data-types.html). Acesso em: 2 jun. 2025.