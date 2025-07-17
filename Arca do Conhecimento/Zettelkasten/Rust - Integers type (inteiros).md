---
Criado: 2025-06-02T10:38
Atualizado: 2025-06-02T10:38
Estudado: 2025-07-16T13:29
Links:
  - "[[Rust - Tipos de dados]]"
---
---
# Rust - Integers type (inteiros)

Um inteiro é um número sem sua parte fracional. Os tipos inteiros em Rust tem as seguintes variantes possíveis:

| Comprimento               | Assinado (`Signed`) | Não assinado (`Unsigned`) | Valores Mínimo / Máximo                                                                                                                                                                                                      |
| ------------------------- | ------------------- | ------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 8-bit                     | `i8`                | `u8`                      | `i8`: -128 → 127  <br> `u8`: 0 → 255                                                                                                                                                                                         |
| 16-bit                    | `i16`               | `u16`                     | `i16`: -32.768 → 32.767  <br> `u16`: 0 → 65.535                                                                                                                                                                              |
| 32-bit                    | `i32`               | `u32`                     | `i32`: -2.147.483.648 → 2.147.483.647  <br> `u32`: 0 → 4.294.967.295                                                                                                                                                         |
| 64-bit                    | `i64`               | `u64`                     | `i64`: -9.223.372.036.854.775.808 → 9.223.372.036.854.775.807  <br> `u64`: 0 → 18.446.744.073.709.551.615                                                                                                                    |
| 128-bit                   | `i128`              | `u128`                    | `i128`: -170.141.183.460.469.231.731.687.303.715.884.105.728 → 170.141.183.460.469.231.731.687.303.715.884.105.727  <br> `u128`: 0 → 340.282.366.920.938.463.463.374.607.431.768.211.455                                     |
| Dependente da arquitetura | `isize`             | `usize`                   | **32-bit:**<br>`isize`: -2.147.483.648 → 2.147.483.647  <br>`usize`: 0 → 4.294.967.295  <br><br> **64-bit:**<br>`isize`: -9.223.372.036.854.775.808 → 9.223.372.036.854.775.807  <br>`usize`: 0 → 18.446.744.073.709.551.615 |


Os inteiros signed podem guardar números de −(2n − 1) to 2n − 1 − 1 inclusive. Já os unsigned guardam números de 0 to 2n − 1.

Os inteiros podem ser escritos das seguintes formas:

| Number literals  | Example       |
| ---------------- | ------------- |
| Decimal          | `98_222`      |
| Hex              | `0xff`        |
| Octal            | `0o77`        |
| Binary           | `0b1111_0000` |
| Byte (`u8` only) | `b'A'`        |

**IMPORTANTE: O tipo padrão de um inteiro é i32.**

## Integer overflow

Quando um valor fora dos valores mínimo/máximo é atribuído a um inteiro, um integer overflow vai ocorrer. Na compilação em modo DEBUG, isso levará o programa a um panic. Já no modo RELEASE não haverá panic mas o valor não será o esperado pois acontecerá o "[_two’s complement wrapping_](https://en.wikipedia.org/wiki/Two%27s_complement)".


---
## References

KLABNIK, Steve; NICHOLSON, Carol. _Data Types_. In: _The Rust Programming Language_. Disponível em: [https://rust-book.cs.brown.edu/ch03-02-data-types.html](https://rust-book.cs.brown.edu/ch03-02-data-types.html). Acesso em: 2 jun. 2025.