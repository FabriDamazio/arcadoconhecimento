---
Criado: 2025-06-19T13:47
Atualizado: 2025-06-19T13:47
Estudado: 2025-06-19T13:47
Links:
  - "[[Programação de computadores]]"
---
---
# Alocação de memória

É o processo de reservar e organizar espaços na memória para armazenar dados durante a execução de um programa.

Ela pode ser dividida em dois grupos principais: estática e dinâmica.

## Alocação estática

Ocorre em tempo de compilação e o espaço de memória é fixado antes da execução (por exemplo variáveis e constantes).

## Alocação dinâmica

Ocorre em tempo de execução e o espaço é alocado e liberado manualmente ou via garbage collector (dependendo da linguagem de programação).  A [[Heap]] tem alocação dinâmica.

### Stack e alocação automática

Quando falamos de **alocação dinâmica**, normalmente estamos falando de **alocação controlada pelo programador**, que pode criar e destruir objetos a qualquer momento, com tamanho flexível, enquanto o programa roda.

A **[[Stack (pilha)]]**, apesar de crescer e diminuir em tempo de execução, **é controlada automaticamente pelo compilador/runtime**, baseada no fluxo de chamadas de função. Por isso, o termo correto é: **"alocação automática"**, não "dinâmica" no sentido clássico.

---
## References

WIKIPEDIA. Alocação de memória. Disponível em: [https://pt.wikipedia.org/wiki/Aloca%C3%A7%C3%A3o_de_mem%C3%B3ria](https://pt.wikipedia.org/wiki/Aloca%C3%A7%C3%A3o_de_mem%C3%B3ria). Acesso em: 19 jun. 2025.