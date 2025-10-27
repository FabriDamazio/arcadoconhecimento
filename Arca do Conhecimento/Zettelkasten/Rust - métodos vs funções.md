---
Criado: 2025-07-28T16:06
Atualizado: 2025-08-11T19:16
Estudado: 2025-07-28T16:06
Links:
  - "[[Rust language]]"
tags:
  - rust
  - programação
---
---
# Rust - métodos vs funções

Em Rust, o que chamamos de métodos e funções possuem uma diferença crucial: funções são blocos de códigos não associados a um tipo (menos as funções associadas, ver mais abaixo). O método é associado a um tipo, operando em uma instância com primeiro argumento sendo `self`. Por exemplo:

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

**Em Rust, o método é apenas um syntax sugar para funções com um parâmetro `self` explícito.**

## Funções associadas (Associated functions)

Uma função criada dentro de um bloco `impl` é chamada de função associada (associated function). Ela é uma função (e não um método) porque ela não tem o `self` como o primeiro parâmetro. Diferente do método associado, a função associada não precisa de uma instância para ser usada. Ela é frequentemente usada para definir construtores que retornam uma nova instância da struct.

```rust
// uma função associada
impl Rectangle {
    fn new(width: u32, height: u32) -> Self {
        Self { width, height }
    }
}
```

Rust não possui uma palavra-chave (keyword) para construtor. A forma idiomática de definir um construtor é criar uma função associada chamada `new` (mas não é obrigatório pela linguagem).

---
## References

**RUST.** _The Rust Programming Language: Method Syntax._ Disponível em: [https://doc.rust-lang.org/book/ch05-03-method-syntax.html](https://doc.rust-lang.org/book/ch05-03-method-syntax.html). Acesso em: 29 jul. 2025.