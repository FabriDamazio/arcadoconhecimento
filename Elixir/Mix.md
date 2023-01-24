Mix é uma ferramenta de build que fornece tarefas (tasks) para criar, compilar e testar proejtos em Elixir, gerenciando suas dependências e muito mais.

## Mix.Project

A fundação do Mix é o projeto, que pode ser definido usando `Mix.Project` em um módulo que geralmente fica em um arquivo chamado `mix.exs`

````elixir
defmodule MyApp.MixProject do
  use Mix.Project

  def project do
    [
      app: :my_app,
      version: "1.0.0"
    ]
  end
end
````

## Mix.Task

Tasks são o que tornam Mix extensível. Mix possui tasks por padrão mas também permite que outras tasks sejam criadas.

Exemplos de tasks:

- **`mix compile`**: compila o projeto.
- **`mix test`**: executa os testes do projeto.
- **`mix run`**: executa um comando em particular dento do projeto.

Projetos podem conter suas próprias tasks personalizadas:

````elixir
defmodule Mix.Tasks.Hello do
  use Mix.Task

  def run(_) do
    Mix.shell().info("Hello world")
  end
end
````

## Dependências

Mix também gerencia suas dependências de forma integrada com o gerenciador de pacotes [[Hex]].

Para usar basta adicionar a chave `deps:` em seu projeto

````elixir
defmodule MyApp.MixProject do
  use Mix.Project

  def project do
    [
      app: :my_app,
      version: "1.0.0",
      deps: deps()
    ]
  end

  defp deps do
    [
      {:ecto, "~> 2.0"},
      {:plug, github: "elixir-lang/plug"}
    ]
  end
end
````

## Environments (ambientes)

Por padrão, os seguintes ambientes são suportados:

-   `:dev` - ambiente padrão
-   `:test` - ambiente onde o  [`mix test`](https://hexdocs.pm/mix/Mix.Tasks.Test.html) é executado
-   `:prod` - ambiente onde suas dependências são executadas

O ambiente pode ser lido utilizando a função `Mix.env/0`

O ambiente pode ser trocado através da linha de comando alterando o valor da variável `$MIX_ENV`:

````
MIX_ENV=prod mix run server.exs
````

Também é possível definir qual dependência esta disponível em cada ambiente:

````elixir
{:some_test_dependency, "~> 1.0", only: :test}
````

## Configuração

### Configuração em tempo de build

Quando um comando Mix é invocado, ele carrega as configurações do arquivo `config/config.exs` caso ele exista. É comum carregar neste arquivo outros arquivos de configuração baseados em ambientes:

````elixir
import Config
config :my_app, :secret_key, System.fetch_env!("MY_APP_SECRET_KEY")
````

### Configuração em tempo de execução

Você pode criar um arquivo de configuração para configurações de runtime. O arquivo `config/runtime.exs` é lido sempre que o projeto é executado.

### Aliases

São atalhos ou tasks específicas do seu projeto. Ao criar uma tasks como mostrado acima, ela estará disponível a todos que usam nosso projeto como dependência. Se quiser que ela seja específica apenas para o projeto, podemos definir uma alias:

````elixir
defmodule MyApp.MixProject do
  use Mix.Project

  def project do
    [
      app: :my_app,
      version: "1.0.0",
      aliases: aliases()
    ]
  end

  defp aliases do
    [
      c: "compile",
      hello: &hello/1
    ]
  end

  defp hello(_) do
    Mix.shell().info("Hello world")
  end
end
````

Para maiores informações sobre o Mix acesse a [documentação oficial](https://hexdocs.pm/mix/Mix.html).


#### Fontes

["Mix docs"](https://hexdocs.pm/mix/Mix.html). https://hexdocs.pm/. Recuperado em 24 de janeiro de 2023.