---
Criado: 2025-07-10T15:30
Atualizado: 2025-07-10T15:30
Estudado: 2025-08-13T16:14
Links:
  - "[[Rust - Tipos de dados]]"
tags:
  - rust
  - programação
---
---
# Rust - Slice type

Slice é um tipo composto representado por `[T]` que permite que uma sequência de elementos contíguos na memória seja referenciado. Ele não possui a posse (ownership) dos dados que referencia, apenas os pega emprestado (borrow). É um _fat pointer_ (ponteiro + tamanho).

## Características principais:

- Um slice é sempre uma **referência**: `&[T]` (imutável) ou `&mut [T]` (mutável).
- Ele armazena **dois dados internamente**: um ponteiro (ptr) para o primeiro elemento e o comprimento (len).
- Utilização:
	- para acessar **parte** de um array, vetor, string, etc., sem copiar os dados.
	- Quando quiser passar uma **parte de uma coleção** para uma função, evitando cópia.
	- Para criar funções genéricas que funcionem com arrays, vetores ou strings.

```rust
// Criando um slice
let a = [1, 2, 3, 4, 5];
let slice: &[i32] = &[1..4];
println!(":?", slice); // output: [2, 3, 4]

// Pode ser omitido o primeiro index caso comeco do zero
let s = String::from("Hello World");
let slice = &[..5];
println!(":?", slice); // output: "Hello"

// Pode ser omitido o último index caso queira até o último elemento
let s = String::from("Hello");
let slice = &[0..];
println!(":?", slice); // output: "Hello"

// Ambos podem ser omitidos caso queira todos elementos
let s = String::from("Hello");
let slice = &[..];
println!(":?", slice); // output: "Hello"
```

---
## References

KLABNIK, Steve; NICHOLSON, Carol. _The Rust Programming Language_. [S. l.]: Rust Project Developers, 2018. Capítulo 4.4 – Slices. Disponível em: [https://rust-book.cs.brown.edu/ch04-04-slices.html](https://rust-book.cs.brown.edu/ch04-04-slices.html). Acesso em: 10 jul. 2025.