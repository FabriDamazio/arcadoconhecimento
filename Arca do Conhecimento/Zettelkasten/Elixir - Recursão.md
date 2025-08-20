---
Criado: 2025-06-02T14:50
Atualizado: 2025-08-20T14:50:00
Estudado: 2025-08-20T11:34:00
Links:
  - "[[Elixir language]]"
---
---
# Elixir - Recursão

A recursão é uma técnica fundamental em Elixir, usada como principal forma de repetição, pois estruturas como `for` e `while` não existem na linguagem. Em vez disso, a linguagem favorece a definição de funções que se chamam a si mesmas com novos parâmetros até atingir uma condição de parada (caso base).

## Conceitos

- Em Elixir, estruturas de repetição tradicionais são substituídas por **recursão + pattern matching**.
- É comum dividir a função em dois (ou mais) cabeçalhos:
  - Um para o **caso base** (condição de parada)
  - Um para o **caso recursivo** (continuação)
  - A linguagem trata **todas as variáveis como imutáveis**, então loops mutáveis não fazem sentido.

```elixir
defmodule ExemploRecursao do
  def soma([]), do: 0 # caso base
  def soma([head | tail]), do: head + soma(tail) # caso recursivo
end

ExemploRecursao.soma([1, 2, 3, 4]) # => 10
```

#  Tail-call optimization

A recursão de cauda (tail call) é uma técnica usada para otimizar chamadas recursivas em linguagens funcionais como Elixir. Ela permite que o compilador substitua a chamada recursiva por um salto (sem adicionar à pilha), evitando estouros de stack em funções profundamente recursivas.

Uma chamada recursiva é considerada **de cauda** quando **é a última operação** realizada por uma função antes de retornar o valor. Nesse exemplo, `conta_regressiva(n - 1)` é a última instrução, portanto é uma **tail call**:

```elixir
def conta_regressiva(0), do: :fim
def conta_regressiva(n) do
  conta_regressiva(n - 1)
end
```

Neste caso, `h + soma(t)` **não** é uma tail call, pois a adição ainda precisa ser feita **depois** da chamada recursiva retornar:

```elixir
def soma(lista), do: soma(lista, 0)

defp soma([], acc), do: acc
defp soma([h | t], acc), do: soma(t, acc) + h

```

### Benefícios

- **Otimização de desempenho:** o compilador pode transformar em loop interno (sem crescer a pilha).
- **Evita estouro de stack:** útil para listas grandes ou chamadas profundas.
- **Código mais funcional:** mantém o estilo funcional e eficiente.

### Dicas de implementação

- Sempre que possível, **use acumuladores** para escrever funções tail-recursive.
- Pode-se usar funções auxiliares (privadas) para esconder os detalhes do acumulador.

---
## References

THE ELIXIR TEAM. _Recursion_. HexDocs. Disponível em: [https://hexdocs.pm/elixir/recursion.html](https://hexdocs.pm/elixir/recursion.html). Acesso em: 2 jun. 2025.