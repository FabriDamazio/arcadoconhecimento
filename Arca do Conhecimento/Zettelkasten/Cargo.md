---
Criado: 2025-05-26T11:18
Atualizado: 2025-05-26T11:18
Estudado: 2025-06-11T11:27
Links:
  - "[[Rust language]]"
---
---
# Cargo

Cargo é a ferramenta oficial de gerenciamento de pacotes, build e dependências para projetos Rust. Ele automatiza a compilação, o download de bibliotecas, a execução de testes e facilita o empacotamento e publicação de crates. Ele usa o arquivo `Cargo.toml` para definir dependências, metadados e configurações do projeto.

Comandos principais:

```bash
cargo new nome_do_projeto       # Cria um novo projeto Rust
cargo build                     # Compila o projeto
cargo run                       # Compila e executa o projeto
cargo test                      # Executa os testes automatizados
cargo check                     # Verifica erros sem compilar completamente
cargo update                    # Atualiza as dependências para as versões mais recentes
cargo publish                   # Publica um crate no crates.io
```

---
## References

KERNIGHAN, Brian W.; RITCHIE, Dennis M. _The Rust Programming Language — Capítulo 1.3: Hello, Cargo_. Brown University. Disponível em: [https://rust-book.cs.brown.edu/ch01-03-hello-cargo.html](https://rust-book.cs.brown.edu/ch01-03-hello-cargo.html). Acesso em: 26 maio 2025.