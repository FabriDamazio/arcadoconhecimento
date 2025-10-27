---
Criado: 2025-08-19T10:44
Atualizado: 2025-08-19T10:44
Estudado: 2025-08-19T10:44
Links:
  - "[[Rust - Enum]]"
tags:
  - rust
  - programação
---
---
# Rust - Option enum

A linguagem Rust não possui valores nulos (null) como em outras linguagens e, para expressar casos onde é importante informar que que um valor não foi informado ou é atualmente inválido, é usado o enum `Option<T>` que é definido na biblioteca padrão.

```rust
// definição do enum na biblioteca padrão
enum Option<T> {
    None,
    Some(T),
}

// criando instâncias do enum
// note que não preciso usar Option::Some pq esta na lib padrão
let algum_numero = Some(5);
let algum_char = Some('e');

// criando uma instância com o valor None
// nela é preciso dizer o tipo para informar o compilador
let sem_valor: Option<i32> = None;

```

Para acessar os valores podemos utilizar os mesmos métodos de um `enum`. 

---
## References

KLABNIK, Steve; NICHOLS, Carol. **The Rust Programming Language**. Brown University, 2023. Disponível em: [https://rust-book.cs.brown.edu/ch06-01-defining-an-enum.html](https://rust-book.cs.brown.edu/ch06-01-defining-an-enum.html). Acesso em: 19 ago. 2025.