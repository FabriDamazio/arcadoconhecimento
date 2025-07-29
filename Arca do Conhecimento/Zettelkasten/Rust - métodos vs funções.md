---
Criado: 2025-07-28T16:06
Atualizado: 2025-07-28T16:06
Estudado: 2025-07-28T16:06
Links:
  - "[[Rust language]]"
---
---
# Rust - métodos vs funções

Em Rust, métodos e funções possui uma diferença crucial: funções são blocos de códigos não associados a um tipo. O método é uma função associada a um tipo, operando em uma instância. Por exemplo:

```rust
// uma função independente
fn soma(a: i32, b: i21) -> i32 {
	a + b
}

// um método associado ao tipo Retangulo
impl Retangulo {
	fn area(&self) -> u32 {
		self.largura * self.altura
	}
}

// o método acima por ser chamado de duas formas
ret.area(); // syntax sugar
Retangulo::area(&ret); 
```

### Syntax sugar para chamada de métodos

As duas maneiras mostradas acima de como chamar um método são traduzidas da mesma maneira. Isso quer dizer que `ret.area()` quando compilado é traduzido para `Retangulo::area(&ret)`.

---
## References

**RUST.** _The Rust Programming Language: Method Syntax._ Disponível em: [https://doc.rust-lang.org/book/ch05-03-method-syntax.html](https://doc.rust-lang.org/book/ch05-03-method-syntax.html). Acesso em: 29 jul. 2025.