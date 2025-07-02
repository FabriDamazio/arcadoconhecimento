---
Criado: 2025-05-27T10:08
Atualizado: 2025-05-27T10:08
Estudado: 2025-07-02T10:55
Links:
  - "[[Elixir Data Structures]]"
---
---
# Elixir - Struct

Uma struct em Elixir é uma estrutura de dados construída sobre o `map`, que permite definir chaves específicas com valores padrões opcionais. Ela proporciona semântica de tipo e validação básica de dados em tempo de compilação.

Elas são imutáveis, tem chaves (campos) definidos explicitamente via macro `defstruct` e são sempre associadas a um módulo.

```elixir
# criando uma struct
defmodule Usuario do
  defstruct nome: "", idade: 0
end

joao = %Usuario{nome: "João", idade: 30}

# acessando e atualizando
joao.nome       # => "João"
joao = %{joao | idade: 31}

# verificação com pattern matching
def saudacao(%Usuario{nome: nome}) do
  "Olá, #{nome}!"
end
``` 

Internamente, structs são apenas **mapas com uma chave `:__struct__`** que aponta para o módulo:

```elixir
%Usuario{nome: "João"} == %{__struct__: Usuario, nome: "João", idade: 0}
```

---
## References

ELIXIR. Structs. HexDocs. Disponível em: https://hexdocs.pm/elixir/structs.html. Acesso em: 27 maio 2025.