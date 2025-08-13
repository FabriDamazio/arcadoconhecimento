---
Criado: 2025-06-19T15:13
Atualizado: 2025-06-19T15:13
Estudado: 2025-08-13T11:09
Links:
  - "[[Alocação de memória]]"
---
---
# Heap

A **heap** é uma área da memória RAM usada para **alocação dinâmica de memória em tempo de execução**. Ela permite que programas solicitem blocos de memória de tamanho variável, com tempo de vida controlado manualmente ou por garbage collectors.

## Funcionamento

- **Alocação dinâmica:** O programador ou o runtime decide quando alocar e desalocar memória.
- **Vida longa e variável:** Dados podem permanecer na memória mesmo após a função que os criou terminar.
- **Custo maior de acesso:** Acesso a dados na heap é mais lento que na stack, devido ao custo de gerenciamento e localização na memória.
- **Fragmentação:** A heap pode sofrer fragmentação com o tempo, dificultando a alocação de blocos grandes.

## Problemas comuns relacionados à Heap

- **Memory Leaks:** Memória alocada que não é liberada.
- **Fragmentação de Memória:** Espaço livre dividido em pequenos blocos, dificultando alocações futuras.
- **Overhead de Garbage Collection:** Em linguagens com GC, pode haver pausas para coleta de lixo.


---
## References

WIKIPEDIA. Alocação de memória. Disponível em: [https://pt.wikipedia.org/wiki/Aloca%C3%A7%C3%A3o_de_mem%C3%B3ria](https://pt.wikipedia.org/wiki/Aloca%C3%A7%C3%A3o_de_mem%C3%B3ria). Acesso em: 19 jun. 2025.