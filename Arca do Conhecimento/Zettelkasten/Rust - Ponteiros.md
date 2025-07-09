---
Criado: 2025-06-16T15:47
Atualizado: 2025-06-16T15:47
Estudado: 2025-07-08T08:51
Links:
  - "[[Rust language]]"
---
---
# Rust - Ponteiros

Um ponteiro é uma variável que armazena o **endereço de memória** de outro valor. Em Rust, isso é feito de maneira **segura**, respeitando as regras de ownership e borrowing.

## Tipos de ponteiros em Rust

Rust fornece vários tipos de ponteiros, cada um com regras e finalidades específicas:

| Tipo                  | Mutável? | Seguro? | Alocação | Uso principal                            |
| --------------------- | -------- | ------- | -------- | ---------------------------------------- |
| `&T`                  | Não      | Sim     | Stack    | Referência imutável                      |
| `&mut T`              | Sim      | Sim     | Stack    | Referência mutável                       |
| `Box<T>`              | Sim      | Sim     | Heap     | Propriedade de um valor heap             |
| `Rc<T>` / `Arc<T>`    | Não      | Sim     | Heap     | Compartilhamento de leitura              |
| `*const T` / `*mut T` | Sim      | Não     | Stack    | Ponteiros brutos para interoperabilidade |

### Referências (`&T`, `&mut T`)

Uma referência pode ser entendida como um "ponteiro seguro". As referências são o tipo mais comum de ponteiro em Rust:

```rust
let x = 5;
let r = &x;      // r é uma referência imutável
let m = &mut x;  // r é uma referência mutável (exclusiva)
```

### Box (alocação na heap)

`Box<T>` é um ponteiro inteligente que aloca o valor na heap. É útil para tipos grandes ou para casos de recursão (como listas ligadas).

```rust
let b = Box::new(10);
println!("{}", *b);  // Dereferência para acessar o valor
```


### Rc e Arc (compartilhamento de ponteiros)

`Rc<T>`: é um ponteiro inteligente , referência contada (single-thread).
`Arc<T>`: é um ponteiro inteligente , versão segura para threads (atomic reference counting).

Permitem múltiplos donos de um valor.

```rust
use std::rc::Rc;

let a = Rc::new(5);
let b = Rc::clone(&a);  // Compartilha ownership
```

### Ponteiros brutos (raw pointer)

Ponteiros como `*const T` e `*mut T` são semelhantes aos de C/C++ e não são seguros. Só podem ser usados dentro de unsafe:
```rust
let x = 10;
let ptr = &x as *const i32;

unsafe {
    println!("{}", *ptr);
}
```

## Dereference  (derreferenciar)

Quando você tem um ponteiro ou uma referência, você não está lidando com o valor em si, mas sim com o endereço de memória onde esse valor está guardado.

    Dereferenciar significa: "acessar o valor para o qual o ponteiro aponta".

Exemplo com referências:

```rust
fn main() {
    let x = 10;
    let y = &x;  // y é uma referência para x

    println!("O valor de x: {}", x);   // Imprime 10
    println!("O valor de y: {}", *y); // Dereferenciando y
}
```

---
## References

KLABNIK, Steve; NICHOLSON, Carol. References and Borrowing. *The Rust Programming Language*, Brown University. Disponível em: https://rust-book.cs.brown.edu/ch04-02-references-and-borrowing.html. Acesso em: 16 jun. 2025.
