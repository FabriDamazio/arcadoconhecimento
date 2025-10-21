---
Criado: 2025-08-14T11:37
Atualizado: 2025-08-14T11:37
Estudado: 2025-08-14T11:37
Links:
  - "[[Rust - Tipos de dados]]"
  - "[[Rust - Option enum]]"
---
---
# Rust - Enum

Enum é uma maneira de definir que um valor esta dentro grupo de valor estabelecido.

As variantes de um `enum` não possuem valores padrão (como números ou strings), sendo simplesmente **identificadores**. Isso quer dizer que o compilador automaticamente associa um valor inteiro para cada variante (geralmente do tamanho de 1 byte) e este valor **não é exposto** no código.

```rust
// definindo um enum com duas variantes possíveis: V4 e V6
enum IpAddrKind {
	V4,
	V6,
}

// Criando instâncias da variante
let a = IpAddrKind::V4;
let b = IpAddrKind::V6;



```

## Armazenando dados em uma variante do Enum

O `enum` também pode ter dados armazenados dentro de suas variantes. Cada variante pode ter diferentes números de dados armazenados e de diferentes tipos (inclusive outro `enum`).

```rust
// definindo dados nas variantes do enum
enum IpAddr {
	V4(u8, u8, u8, u8),
	V6(String),
}

// criando uma instância informando os dados
let home = IpAddr::V4(127, 0, 0, 1);
let loopback = IpAddr::V6(String::from("::1"));
```

## Definindo métodos

É possível definir métodos no `enum`.

```rust
impl IpAddr {
	fn test(&self) {
		// implementação do body do método aqui
	}
}

let home = IpAddr::V4(127, 0, 0, 1);
home.test();
```

## Acessando dados do Enum

### **Resumo das Opções**

| Método              | Quando Usar?                             |
| ------------------- | ---------------------------------------- |
| **`match`**         | Quando precisa tratar todas as variantes |
| **`if let`**        | Quando só interessa uma variante         |
| **Métodos no Enum** | Para encapsular a lógica de acesso       |
| **`let` + `else`**  | Quando tem certeza da variante           |
Exemplos:

```rust
// dado o seguinte enum
let home = IpAddr::V4(127, 0, 0, 1);

// match
match home {
	IpAddr::V4(a, b, c, d) => {
		// ...
	}
	IpAddr::V6(addr) => {
		// ...
	}
}

// if let
if let IpAddr::V4(a, b, c, d) = home {
	// ...
}

// Métodos no Enum
impl IpAdrr {
	fn unwrap(&self) -> (u8, u8, u8, u8) {
		// acessa os dados usando match por exemplo
	}
}

// let + else
let IpAddr::V4(a, b, c, d) = home else {
	panic!("Não é Ipv4!");
};

```



---
## References

KLABNIK, Steve; NICHOLS, Carol. **The Rust Programming Language**. Brown University, 2023. Disponível em: [https://rust-book.cs.brown.edu/ch06-01-defining-an-enum.html](https://rust-book.cs.brown.edu/ch06-01-defining-an-enum.html). Acesso em: 19 ago. 2025.