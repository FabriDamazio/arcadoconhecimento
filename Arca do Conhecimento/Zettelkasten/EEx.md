---
Criado: 2024-11-14T14:52
Atualizado: 2025-05-23T14:06
Estudado: 2025-07-18T10:49
Links:
  - "[[Elixir language]]"
---
---
# EEx

O módulo EEx (Embedded Elixir) permite que um código escrito em Elixir seja incorporado dentro de uma string.  As principais APIs do módulo são:

- `eval_string/3` avalia uma string diretamente. É a mais simples porém a mais lenta porque o código é avaliado em runtime.

```elixir
iex> EEx.eval_string("foo <%= bar %>", bar: "baz")
"foo baz"
```

- `eval_file/3` avalia um arquivo diretamente. É a mais simples porém a mais lenta porque o código é avaliado em runtime.

```elixir

# sample.eex
foo <%= bar %>

# IEx
EEx.eval_file("sample.eex", bar: "baz")
#=> "foo baz"
```

 - `function_from_string/5` define uma função a partir de uma string para a incorporar como uma função em um módulo que então é compilado. É a maneira mais indicada se tiver acesso ao template em tempo de compilação.

```elixir
iex> defmodule Sample do
...>  require EEx
...>  EEx.function_from_string(:def, :sample, "<%= a + b %>", [:a, :b])
...> end
iex> Sample.sample(1, 2)
"3"
```

 - `function_from_file/5` define uma função de um arquivo para a incorporar esse template como uma função em um módulo que então é compilado. É a maneira mais indicada se tiver acesso ao template em tempo de compilação.

```elixir
# sample.eex
<%= a + b %>

# sample.ex
defmodule Sample do
  require EEx
  EEx.function_from_file(:def, :sample, "sample.eex", [:a, :b])
end

# iex
Sample.sample(1, 2)
#=> "3"
```

## Tags

As tags suportadas pelo EEx são

```elixir
<% Elixir expression: executa o código mas descarta o output %>
<%= Elixir expression: executa o código e printa o resultado %>
<%% EEx quotation: retorna o conteúdo dentro da tag como ele é %>
<%!-- Comments: discartado do source --%>
```

Mais informações sobre as `options` aceitas pelas funções e sobre a engine do EEX podem ser consultadas no [link da documentação oficial](https://hexdocs.pm/eex/EEx.html).

---
## References

EEX - Embedded Elixir. Disponível em: [https://hexdocs.pm/eex/EEx.html](https://hexdocs.pm/eex/EEx.html). Acesso em: 14 nov. 2024.