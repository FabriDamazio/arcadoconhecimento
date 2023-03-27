Maps é uma estutura de dados de pares de chave-valor.

Características:

- Não possui restrição ao tipo da chave
- Os pares de chave-valor não seguem nenhum tipo de ordem
- Não permite chaves duplicadas
- Possui uma sintaxe mais simples caso a chave seja um atom
- Caso use a sintaxe comum e a mais simples no mesmo mapa a mais simples deve vir por ultimo
- Para acessar o valor da chave pode ser usado as funções deste módulo `Map.get/3`, `Map.fetch/2` ou utilizando a sintaxe `map[]` do módulo `Access`.
- Uma chave do tipo atom pode ter seu valor acessado utilizando a notação de ponto `map.key`
- Para adicionar ou atualizar valores de chaves existem diferentes funções neste módulo como `Map.put/3`, `Map.put_new/3`, `Map.update!/3`, `Map.update/4` entre outros. Existem também uma sintaxe específica para atualizar o valor de uma chave existente (exemplo abaixo)

Pode ser criada utilizando a sintaxe `%{}`

````elixir
# Mapa vazio
iex> %{}
%{}
# mapa com chaves em string
iex> %{"one" => :one, "two" => :two}
%{"one" => :one, "two" => :two}
````

Sintaxe mais simples para chaves do tipo atom:

````elixir
iex> %{one: "one", two: "two"}
%{one: "one", two: "two"}
````

Misturando os dois tipos de sintaxe (com a mais simples por último):

````elixir
iex> %{:two => "two", "one" => :one}
%{:two => "two", "one" => :one}
````

Acessando chaves no mapa

````elixir
iex> map = %{:two => "two", "one" => :one}
%{:two => "two", "one" => :one}

# utilizando Map.fetch
iex> Map.fetch(map, :two)
{:ok, "two"}

# utilizando Map.get
iex> Map.get(map, :two)
"two"

#utilizando map[]
iex> map[:two]
"two"

# utilizando a notação de ponto (apenas para atoms)
iex> map.two
"two"
````

Sintaxe específica para atualizar o valor de uma chave existente (caso a chave não exista temos um `KeyError` ):

````elixir
iex> map = %{one: 1, two: 2}
iex> %{map | one: "one"}
%{one: "one", two: 2}
````

