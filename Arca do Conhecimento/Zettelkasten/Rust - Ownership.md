---
Criado: 2025-06-12T13:05
Atualizado: 2025-06-12T13:05
Estudado: 2025-06-12T13:05
Links:
  - "[[Rust language]]"
---
---
# Rust - Ownership

O sistema de **ownership (propriedade)** é o mecanismo central de gerenciamento de memória em Rust. Ele permite que o compilador garanta **segurança de memória e ausência de vazamentos** sem precisar de garbage collector.

Neste caso, **segurança significa ausência de comportamentos indefinidos**. Rust os previne com verificações em tempo de compilação e não em tempo de execução. A linguagem não permite gerenciamento manual de memória.

---
## Conceitos principais

### 1. Ownership (propriedade)
Cada valor em Rust tem um **dono** (owner), que é uma variável. Um valor só pode ter **um dono por vez**.

### 2. Move (movimentação)
Ao atribuir uma variável a outra, a **posse (ownership) é transferida**:

```rust
let s1 = String::from("hello");
let s2 = s1; 
// s1 é movido para s2 
// e não pode mais ser usado
```

### Borrowing (empréstimo)

É possível emprestar o valor a outra variável ou função por meio de referência (&T):

```rust
fn print_str(s: &String) {
    println!("{}", s);
}
```

### Drop

Quando a variável que possui um valor sai do escopo, a memória é automaticamente liberada com `drop`.

```rust
{
    let s = String::from("bye");
} // s é dropado aqui
```

---
## Regras de ownership

- Cada valor tem um único dono.
- Quando o dono sai do escopo, o valor é desalocado.
- Valores são movidos, não copiados (a não ser que implementem Copy).
- Apenas uma referência mutável por vez, ou várias imutáveis.
- As referências não podem ser usadas depois que o valor original foi movido ou dropado.

---
## References

KLABNIK, Steve; NICHOLSON, Carol. Safety is the absence of undefined behavior. In: The Rust Programming Language. Brown University Computer Science. Disponível em: https://rust-book.cs.brown.edu/ch04-01-what-is-ownership.html#safety-is-the-absence-of-undefined-behavior. Acesso em: 5 jun. 2025.
