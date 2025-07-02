---
Criado: 2025-06-05T21:33
Atualizado: 2025-06-05T21:33
Estudado: 2025-06-27T15:55
Links:
  - "[[Rust language]]"
---
---
# Rust - Statements e Expressions

Em Rust, há uma distinção clara entre **statements** (declarações) e **expressions** (expressões). Essa diferença é fundamental para entender como o fluxo de controle e atribuição funcionam na linguagem.

## Expression (expressão)

Uma **expressão** **avalia para um valor** e possui um **tipo**. Pode ser usada como parte de outra expressão ou em uma atribuição.

Exemplos:

```rust
5 + 3       // expressão que avalia para 8
"texto"     // expressão que avalia para um &str
some_func() // expressão cujo valor é o retorno da função
```

Um bloco de código entre `{}` é uma **expressão**. O **valor do bloco** é a última expressão **sem ponto e vírgula**:

```rust
let y = {
    let x = 3;
    x + 1  // valor do bloco: 4
};
```

Um `;` no final de uma expressão **a transforma em um statement**, descartando seu valor:

```rust
// Expressão (sem ponto e vírgula)
let z = {
    2 + 2
}; // z recebe 4

// Statement (com ponto e vírgula)
let z = {
    2 + 2;
}; // z recebe () (unit)
```

## Statement (declaração)

Uma **declaração** executa uma ação, mas **não retorna um valor útil**. Statements geralmente terminam com `;` e podem incluir declarações de variáveis ou chamadas de função com efeitos colaterais.

Exemplos:
```rust
let x = 5;         // declaração (de atribuição)
println!("{}", x); // declaração (efeito colateral)
```


---
## References

KLABNIK, Steve; NICHOLSON, Carol. How functions work. In: The Rust Programming Language. Brown University Computer Science. Disponível em: https://rust-book.cs.brown.edu/ch03-03-how-functions-work.html. Acesso em: 5 jun. 2025.
