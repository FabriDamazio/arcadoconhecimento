---
Criado: 2025-06-02T10:24
Atualizado: 2025-06-02T10:24
Estudado: 2025-06-02T10:24
Links:
  - "[[Rust language]]"
---
---
# Rust - Constantes

São valores associados a um nome e que não podem ser alterados. Diferentemente de variáveis, são sempre imutáveis (não é possível utilizar `mut` para torná-las mutáveis). Seu valor deve ser sempre uma expressão constante e não um resultado de um valor que pode ser apenas computado em runtime.

Exemplo:

```rust
const THREE_HOURS_IN_SECONDS: u32 = 60 * 60 * 3;
```

---
## References

KLABNIK, Steve; NICHOLSON, Carol. _Variables and Mutability_. In: _The Rust Programming Language_. Disponível em: [https://rust-book.cs.brown.edu/ch03-01-variables-and-mutability.html](https://rust-book.cs.brown.edu/ch03-01-variables-and-mutability.html). Acesso em: 2 jun. 2025.
