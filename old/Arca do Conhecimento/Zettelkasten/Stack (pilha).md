---
Criado: 2025-06-19T15:10
Atualizado: 2025-06-19T15:10
Estudado: 2025-08-13T11:08
Links:
  - "[[Alocação de memória]]"
---
---
# Stack (pilha)

A **stack** (ou pilha) é uma estrutura de dados que funciona no princípio **LIFO** (Last In, First Out), usada em programação para armazenar variáveis locais, parâmetros de funções e endereços de retorno durante a execução de um programa.

## Funcionamento

- A stack cresce e diminui conforme funções são chamadas e retornam.
- Cada chamada de função cria um **stack frame**, que contém suas variáveis locais e informações para retornar ao chamador.
- Quando a função termina, seu frame é removido da stack automaticamente.

## Características principais

- Alocação automática e rápida de memória.
- Tamanho limitado, podendo causar **stack overflow** em casos de recursão muito profunda.
- Gerenciada pelo sistema operacional e CPU.

## Uso típico

- Armazenar variáveis locais.
- Controlar o fluxo de execução (endereço de retorno).
- Passagem de parâmetros de funções (em algumas arquiteturas).

---
## References

WIKIPEDIA. Alocação de memória. Disponível em: [https://pt.wikipedia.org/wiki/Aloca%C3%A7%C3%A3o_de_mem%C3%B3ria](https://pt.wikipedia.org/wiki/Aloca%C3%A7%C3%A3o_de_mem%C3%B3ria). Acesso em: 19 jun. 2025.