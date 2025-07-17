---
Criado: 2025-07-17T11:38
Atualizado: 2025-07-17T11:38
Estudado: 2025-07-17T11:38
Links:
  - "[[Elixir Data Structures]]"
---
---
# Elixir - Keyword list

É uma lista que tem exclusivamente tuplas de dois elementos. O primeiro elemento (chamado de chave ou key) é um `atom` e o segundo elemento (chamado de valor ou value) é um valor associado.

Uma Keyword list tem algumas características importantes, como:
	- Pode ter chaves duplicadas então não é estritamente uma estrutura de dados de chave-valor.
	- Preserva a ordem dos elementos.
	- Tem a performance de O(n) para buscas portante não deve ser usada para dados grandes.

Ela é usada principalmente como parâmetros de funções (options) e configurações simples.

Exemplos de uso:

```elixir
# Criando uma Keyword list
x = [nome: "Lu", cidade: "Curitiba"]

# Acessando seus valores
# com colchetes
x[:nome] # => "Lu"
x[:idade] # => nil (chave não existe)
#com get
Keyword.get(x, :nome) # => "Lu"
Keyword.get(x, :idade) #=> 0 (default)
# com fetch
Keyword.fetch!(x, :nome) # => "Lu"
Keyword.fetch!(x, :idade) # => (KeyError) key :idade not found

# Adicionando um elemento
x = [idade: 30] ++ x

# Adicionando ou atualizando um elemento caso exista
x = Keyword.put(x, :nome, "Fabricio")

# Removendo um elemento
x = Keyword.delete(x, :idade) # => [nome: "Fabricio", cidade: "Curitiba]
{cidade, x} = Keyword.pop(x, :cidade) 
cidade # => "Curitiba"
x # => [nome: "Fabricio"]
```

---
## References

ELIXIR. **Keyword**. [S. l.], 2025. Disponível em: <https://hexdocs.pm/elixir/Keyword.html>. Acesso em: 17 jul. 2025.