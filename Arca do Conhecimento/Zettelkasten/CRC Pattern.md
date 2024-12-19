2024-12-19 - 10:10
Status: #idea
Tags: [[Elixir language]]

# CRC Pattern (por Bruce Tate)

O padrão CRC (Construir - Reduzir - Converter) é um conceito apresentado pelo autor Bruce Tate em seus livros e cursos. Ele demonstra que este padrão de implementação aparece em diversos lugares como plug, genserver, ecto, entre outros. 

**Podemos utilizar esse padrão para simplificar nossas implementações.**

De forma geral, criamos estruturas de dados iniciais, processamos essas estruturas e convertemos esses dados para o formato desejados.  Explicando detalhadamente cada etapa:

- Construir (construct)

Cria os dados iniciais para poderem ser processados.

```elixir
iex> starting_values = [1, 2, 3]
#[1, 2, 3]
```

- Reduzir  (reduce)

Processa os valores iniciais para condensá-los em um resultado desejado.

```elixir
iex>def reduzir(values) do: 
>   Enum.reduce(values, 0, fn x, acc -> x + acc end)
> end
```


- Converter  (convert)

Transforma o resultado em um formato desejado para ser consumido.

```elixir
iex>def converter(resultado) do: 
>   "O resultado é #{resultado}."
> end
```

A versão final do CRC ficaria:

```elixir
iex> starting_values |> reduzir |> converter
# "O resultado é 6."
```

## Onde este padrão é usado?

O `Plug` utiliza este padrão. Ele recebe os dados iniciais, processa e converte no resultado. 

Um `Genserver` constrói os dados na função `init/1`, reduz os dados nas funções `handle_cast/2` e `handle_call/3` e por fim converte o resultado na camada de API.

Uma LiveView constrói os dados na função `mount/3`, os reduz na função `handle_event/3` e converte na função `render/1`.

---

# References

**RED RAPIDS.** _Learning Elixir: It’s all reduce._ Medium, 12 abr. 2016. Disponível em: [https://redrapids.medium.com/learning-elixir-its-all-reduce-204d05f52ee7](https://redrapids.medium.com/learning-elixir-its-all-reduce-204d05f52ee7). Acesso em: 19 dez. 2024.