---
Criado: 2025-07-03T14:09
Atualizado: 2025-07-03T14:09
Estudado: 2025-07-30T15:38
Links:
  - "[[Rust - Ownership]]"
tags:
  - rust
  - programação
---
---
# Rust - Borrow Checker

O Borrow Checker é um componente contido no compilador responsável por garantir a segurança de memória, analisando (em tempo de compilação) as referências de dados e verificando se suas regras de propriedade (ownership) e ciclo de vida são respeitadas.

Ele funciona como um sistema de **controle de permissões sobre places (lugares)**, garantindo a segurança da memória **sem custos em tempo de execução**, ao modelar e validar o uso das referências estaticamente.

## O conceito de Place (lugar)

O Borrow Checker trabalha com o conceito de "place" (lugar). Place é qualquer expressão que pode aparecer à esquerda de uma atribuição:

	- a   - uma variável
	- *a  - dereference
	- a[0]  - acceso a elemento de array
	- a.field  - campos de tuplas e structs
	- *((a[0].1)  - qualquer tipo de combinação mais complexa como essa

## Funcionamento 

Em tempo de compilação, o Borrow Checker trabalha com permissões estáticas sobre places (lugares). Cada place possui permissões que determinam o que pode ser feito com seus dados. São 3 tipos de permissões:

	- R (READ): pode ser lido (copiado para outro lugar).
	- W (WRITE): pode ser mutado.
	- O (OWN): pode ser movido ou descartado.

Vale ressaltar que estas permissões não existem em tempo de execução. Elas formam apenas um modelo usado pelo Borrow Checker para verificar a segurança do código quanto ao uso da memória.

Exemplo básico mostrando as permissões dos places:

```rust
// Exemplo sem violação de permissão

// v tem permissões +R +W +O
let mut v: Vec<i32> = vec![1, 2, 3];
// num pega emprestado os dados e ganha +R e +O
// v empresta os dados e perde W e O
let num: &i32 = &v[2];    
// uso de num devolve os dados para v que ganha W e O
println!("{}", num);    
// push vai fazer a mutação de v e é válido pq v tem permissão W
v.push(4);                          

// ------------------------------
// Exemplo de permissão violada

// v tem permissões +R +W +O
let mut v = vec![1, 2, 3];
// num pega emprestado os dados e ganha +R e +O
// v empresta os dados e perde W e O
let num = &v[2];
// ERRO: v não tem permissão W de escrita
// os dados estão emprestados para num
v.push(4);                     
println!("{}", *num);

// ------------------------------
// Exemplo sem violação com referência mutável

// v tem permissões +R +W +O
let mut v = vec![1, 2, 3];
// num pega emprestado os dados e ganha +R e +O
// v empresta os dados e perde R, W e O
// *num ganha permissões +R e +W
// isso acontece porque num é uma referência mutável
let num: &mut i32 = &mut v[2];
// o valor de num pode ser mutado usando *num que possui W
*num += 1;*
// Após o uso o ownership dos dados é devolvido a v
// As permissões +R +W e +O retornam a v
println!("Thied element is {}", *num);
```



---
## References

KLABNIK, Steve; NICHOLSON, Carol. _The Rust Programming Language – References and Borrowing_. Disponível em: [https://rust-book.cs.brown.edu/ch04-02-references-and-borrowing.html](https://rust-book.cs.brown.edu/ch04-02-references-and-borrowing.html). Acesso em: 3 jul. 2025.