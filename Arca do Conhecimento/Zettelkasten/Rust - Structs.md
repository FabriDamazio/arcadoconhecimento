---
Criado: 2025-07-21T16:27
Atualizado: 2025-07-21T16:27
Estudado: 2025-07-21T16:27
Links:
  - "[[Rust - Tipos de dados]]"
tags:
  - rust
  - programação
---
---
# Rust - Structs

É um tipo de dado que agrupa valores relacionados sob um mesmo nome. São similares as tuplas e, como elas, seus campos podem ter diferentes tipos de dados. Diferentemente das tuplas, é necessário nomear cada um dos seus campos e eles não possuem uma ordem definida.

Em relação a mutabilidade dos dados, a instância toda deve ser mutável ou imutável. Não é possível controlar os campos isoladamente.

Para definir uma `struct`, devemos utilizar a palavra `struct` seguida de seu nome e os nomes dos seus campos.   Exemplos de uso de uma struct:

```rust
// definindo uma struct
struct User {
	active: bool,
	username: String,
	email: String,
	sign_in_count: u64,
}

// instanciando uma struct
let user1 = User {
	email: String::from("teste@teste.com"),
	username: String:: from("username123"),
	active: true,
	sign_in_count: 1,
};

// o valor de um campo é acessado com dot notation
user1.email;
user1.username;

// atualizando um campo de uma struct mutável
user1.email = String::from("teste2@teste.com");

// criando uma função que instancia um User
fn build_user(email: String, username: String) -> User {
	User {
		active: true,
		sign_in_count: 1,
		username: username,
		email: email,
	}
}

// simplificando a função usando mesmo nome nos parametros e nos campos
fn build_user(email: String, username: String) -> User {
	User {
		active: true,
		sign_in_count: 1,
		username,
		email,
	}
}

// instanciando com base nos dados de outra struct
let user2 = User {
	active: user1.active,
	username: user1.username,
	email: String::from("another@email.com"),
	sign_in_count: user1.sign_in_count,
};

// instanciando usando a struct update syntax
let user2 = User {
	email: String::from("another@email.com"),
	..user1
};

```

### Tuple Structs

Rust também suporta `struct` que são similares a tuplas, chamadas de tuple structs. São structs que possuem um nome porem seus campos não tem nomes associados a eles. Tuple structs são úteis quando você quedar um nome e fazer esta tupla diferente das outras como no exemplo abaixo:

```rust
struct Color(0, 0, 0);
struct Point(0, 0, 0);

let black = Color(0, 0, 0);
let origin = Point(0, 0, 0);
```

### Unit-Like Structs

Podemos declarar uma `struct` que não possui nenhum campo. Ela é chamada de unit-like struct porque elas tem comportamento similar a um unit type `()`. São úteis quando é preciso implementar uma trait em algum tipo mas sem a necessidade de guardar dados.

```rust
struct AlwaysEqual;

let subject = AlwaysEqual;
```



---
## References

BROWN UNIVERSITY. **The Rust Programming Language**: Defining and Instantiating Structs. Disponível em: [https://rust-book.cs.brown.edu/ch05-01-defining-structs.html](https://rust-book.cs.brown.edu/ch05-01-defining-structs.html). Acesso em: 21 jul. 2025.