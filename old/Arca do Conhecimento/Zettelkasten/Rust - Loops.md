---
Criado: 2025-06-23T18:02
Atualizado: 2025-06-23T18:02
Estudado: 2025-08-13T16:19
Links:
  - "[[Rust language]]"
---
---
# Rust - Loops

Usados para executar repetidamente um bloco de código, a linguagem possui três tipos de estruturas de repetição (loops): `loop`, `while` e `for`.

## Loop

O `loop` repete a execução do bloco de código até que seja explicitamente parado. Ele pode ser parado utilizando `break` ou `return`. A diferença é que utilizando `break`, o loop termina, mas o código depois dele continua normalmente. Já utilizando  `return`, toda a função termina na hora, e o que vem depois do loop nem chega a ser executado.

Ao utilizar `continue`,  o loop continua, porém não executa o restante do código daquela repetição. É possível retornar um valor do `loop` adicionando o valor que quer retornar logo após o `break`.

```rust
fn main() {
    let mut counter = 0;

    let result = loop {
        counter += 1;

        if counter == 10 {
            break counter * 2;
        }
    };

    println!("The result is {result}");
}
```

Um loop pode ter uma identificador (label) para que, em casos de múltiplos loops aninhados, uma chamada de `break` ou `continue` saiba de qual loop se trata. Caso não use o identificador, o loop mais interno que é usado.

Um nome de um identificador tem que começar com aspa simples, como neste exemplo: 

```rust
fn main() {
    let mut count = 0;
    'counting_up: loop {
        println!("count = {count}");
        let mut remaining = 10;

        loop {
            println!("remaining = {remaining}");
            if remaining == 9 {
                break;
            }
            if count == 2 {
                break 'counting_up;
            }
            remaining -= 1;
        }

        count += 1;
    }
    println!("End count = {count}");
}
```

## While

Executa o bloco de código enquanto a condição for verdadeira.

```rust
fn main() {
    let mut number = 3;

    while number != 0 {
        println!("{number}!");

        number -= 1;
    }

    println!("LIFTOFF!!!");
}
```

## For

Itera sobre um range, array, iterator (ou qualquer coisa que implementar `IntoIterator`). O uso mais comum é para percorrer uma coleção ou sabe exatamente quantas iterações precisa. Para coleções é considerado mais seguro que o `while` porque ele não torna possível acessar um index não existente na coleção.

```rust
fn main() {
	let a = [10, 20, 30, 40, 50];

	for element in a {
		println!("the value is: {element});
	}
}
```

---
## References

KLABNIK, Steve; NICHOLSON, Carol. _The Rust Programming Language - Control Flow_. Disponível em: [https://rust-book.cs.brown.edu/ch03-05-control-flow.html](https://rust-book.cs.brown.edu/ch03-05-control-flow.html). Acesso em: 23 jun. 2025.