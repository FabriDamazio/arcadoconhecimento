---
Criado: 2025-06-05T21:05
Atualizado: 2025-06-05T21:05
Estudado: 2025-06-05T21:05
Links:
  - "[[Rust - Tipos de dados]]"
  - "[[Rust - Tupla]]"
---
---
# Rust - Unit type

O tipo `()` em Rust representa uma **tupla vazia**, também conhecido como o **tipo unit**. Ele indica que não há valor significativo a ser retornado ou armazenado, mas ainda assim é um valor válido no sistema de tipos da linguagem.

## Características principais

- `()` é o **único valor possível** do tipo unit.
- O tipo unit possui **zero bytes de tamanho**.
- É utilizado como retorno padrão de funções que não retornam valor útil (semelhante ao `void` em C).
- Pode ser utilizado em tuplas e em expressões que produzem efeito colateral.

## Exemplos

### Função que retorna `()`

```rust
// Essa função retorna `()` implicitamente.
fn saudacao() {
    println!("Olá!");
};

// Explicitamente
fn saudacao() -> () {
    println!("Olá!");
};

// `resultado` é do tipo ()
let resultado = {
    println!("Executando bloco");
};
```

---
## References

KLABNIK, Steve; NICHOLSON, Carol. _Data Types_. In: _The Rust Programming Language_. Disponível em: [https://rust-book.cs.brown.edu/ch03-02-data-types.html](https://rust-book.cs.brown.edu/ch03-02-data-types.html). Acesso em: 5 jun. 2025.