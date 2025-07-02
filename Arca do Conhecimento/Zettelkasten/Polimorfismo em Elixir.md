---
Criado: 2024-12-19T14:05
Atualizado: 2025-06-09T10:28
Estudado: 2025-07-02T10:50
Links:
  - "[[Elixir language]]"
  - "[[Behaviour]]"
  - "[[Protocol]]"
  - "[[Processos]]"
---
---
# Polimorfismo em Elixir

Em uma linguagem de programação que utiliza o paradigma orientado a objetos, podemos pensar em um objeto como sendo um acoplamento entre estado, comportamento e mutabilidade (ou tempo, em relação ao dado sendo alterado ao longo do tempo). Sempre que criamos um objeto, essas três dimensões estão presentes.

![[objectoop.png]]

Do ponto de vista do Elixir, estas três dimensões estão desacoplados. Comportamentos são definidos por módulos, estado pelos dados e a mutabilidade pelos processos.

![[objectsbyelixir.png]]

Sendo assim podemos ter polimorfismo em cada uma dessas dimensões separadamente:

- Na dimensão comportamento , implementando um `Behaviour` no módulo:

```elixir
# definindo um Behaviour
defmodule Speaker do
  @callback greet(name :: String.t()) :: String.t()
end

# criando as implementações
defmodule EnglishSpeaker do
  @behaviour Speaker

  @impl Speaker
  def greet(name), do: "Hello, #{name}!"
end

defmodule SpanishSpeaker do
  @behaviour Speaker

  @impl Speaker
  def greet(name), do: "¡Hola, #{name}!"
end

# utilizando o polimorfismo
defmodule Greeter do
  def say_hello(module, name) do
    module.greet(name)
  end
end

# exemplo de uso
Greeter.say_hello(EnglishSpeaker, "Alice")
# => "Hello, Alice!"

Greeter.say_hello(SpanishSpeaker, "Alice")
# => "¡Hola, Alice!"


```


- Na dimensão estado, implementando um  `Protocol`:

```elixir
# definindo um Protocol
defprotocol Stringify do
  @doc "Converte o dado para uma string personalizada"
  def to_string(data)
end

# implementando o Procotol para integer
defimpl Stringify, for: Integer do
  def to_string(num), do: "Número inteiro: #{num}"
end

# implementando o Protocol para Map
defimpl Stringify, for: Map do
  def to_string(map), do: "Mapa com chaves: #{inspect(Map.keys(map))}"
end

# Usando o Protocol
Stringify.to_string(42)
# => "Número inteiro: 42"

Stringify.to_string(%{nome: "Alice", idade: 30})
# => "Mapa com chaves: [:nome, :idade]"

```

- Na dimensão mutabilidade, criando um processo:

```elixir
# definindo o processo CAT
defmodule CatProcess do
  def start do
    spawn(fn -> loop() end)
  end

  defp loop do
    receive do
      {:speak, sender} ->
        send(sender, {:response, "meow"})
        loop()
    end
  end
end

# definindo o processo DOG
defmodule DogProcess do
  def start do
    spawn(fn -> loop() end)
  end

  defp loop do
    receive do
      {:speak, sender} ->
        send(sender, {:response, "woof"})
        loop()
    end
  end
end

# definindo um cliente polimórfico
defmodule AnimalClient do
  def speak(animal_pid) do
    send(animal_pid, {:speak, self()})

    receive do
      {:response, sound} -> sound
    after
      1000 -> "no response"
    end
  end
end

# usando este cliente
cat = CatProcess.start()
dog = DogProcess.start()

AnimalClient.speak(cat)
# => "meow"
AnimalClient.speak(dog)
# => "woof"
```


---
## References

**VALIM, José.** _Keynote: Gang of None? Design Patterns in Elixir._ ElixirConf EU 2024, YouTube, 2024. Disponível em: [https://youtu.be/agkXUp0hCW8](https://youtu.be/agkXUp0hCW8). Acesso em: 19 dez. 2024.