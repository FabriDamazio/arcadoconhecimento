---
Criado: 2025-05-29T11:35
Atualizado: 2025-05-29T11:35
Estudado: 2025-05-29T11:35
Links:
  - "[[Rust language]]"
---
---
# Rust - Variáveis

Na linguagem Rust as variáveis são imutáveis por padrão. Elas podem ser mutáveis adicionando `mut` antes do nome da variável.

```rust
let x = 2; // imutável
let mut y = 3; // mutável
```

Ao tentar atribuir um novo valor a uma variável imutável, temos um erro de compilação

```rust
let x = 2; // imutável
x = 3; // aqui temos um erro de compilação - error[E0384]: cannot assign twice to immutable variable `x` 
```

Rust também permite "shadowing", que é declarar uma nova variável com o mesmo nome de uma variável previamente declarada. Shadowing é diferente de criar uma variável mutável porque estamos efetivamente criando uma nova variável e sendo assim ela também respeita o escopo de declaração e uso como demonstra o exemplo abaixo:

```rust
let x = 5;
let x = x + 1;

{
    let x = x * 2;
	println!("The value of x in the inner scope is: {x}");
}

println!("The value of x is: {x}");

// resultado ao executar:
// The value of x in the inner scope is: 12
// The value of x is: 6
```

---
## References

KLABNIK, Steve; NICHOLSON, Carol. **Variables and Mutability**. In: _The Rust Programming Language_. [S. l.]: Brown University, [202-?]. Disponível em: [https://rust-book.cs.brown.edu/ch03-01-variables-and-mutability.html](https://rust-book.cs.brown.edu/ch03-01-variables-and-mutability.html). Acesso em: 29 maio 2025.