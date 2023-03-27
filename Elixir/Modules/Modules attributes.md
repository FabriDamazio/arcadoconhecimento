Atributos tem 3 finalidades:

- Fazer uma anotação em um modulo para ser usado pelo usuário ou pela VM.
- Funcionar como constantes.
- Funcionar como um armazenamento temporário durante a compilação.


## Annotations

````elixir
defmodule Math do  
	@moduledoc """
	Provides math-related functions.

	  ## Examples

	      iex> Math.sum(1, 2)
	      3

	"""
end
````

-   `@moduledoc` - para documentar o módulo.
-   `@doc` - para documentar uma função ou macro abaixo do atributo.
-   `@spec` - typespec para a função abaixo do atributo.
-   `@behaviour` - especificar um behaviour.

## Constantes

Pode ser usada caso queira deixar o valor mais visível ou reusável.

```elixir
defmodule MyApp.Status do

  @service URI.parse("https://example.com")

  def status(email) do
    SomeHttpClient.get(@service)
  end
end
```

Atenção: o valor da constante é definido em tempo de compilação e não em tempo de runtime.

Quando você repete um atributo no módulo o valor dele é reatribuído ao novo valor. Caso queira acumular os valores é necessário alterar o comportamento no módulo

```elixir
defmodule Foo do
  Module.register_attribute __MODULE__, :param, accumulate: true

  @param :foo
  @param :bar
  # here @param == [:bar, :foo]
end
```

## Armazenamento temporário

```elixir
defmodule MyTest do
  use ExUnit.Case, async: true

  @tag :external
  @tag os: :unix
  test "contacts external service" do
    # ...
  end
end
```

No exemplo acima, ExUnit armazena o valor de async: true em um atributo de módulo para alterar como o módulo é compilado. As tags também são definidas como acumuladores: atributos que armazenam tags que podem ser usadas para configurar e filtrar testes.
Para entender melhor como funciona é necessário conhecer sobre macros.