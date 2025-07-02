---
Criado: 2025-01-26T14:13
Atualizado: 2025-05-23T17:29
Estudado: 2025-07-02T10:55
Links:
  - "[[Padrões para resolver problemas de algoritmos e estrutura de dados]]"
---
---
# Two pointers

O padrão **Two Pointers** (ou "Dois Ponteiros") é uma técnica eficiente para resolver problemas que envolvem arrays ou listas, especialmente quando você precisa encontrar pares de elementos que satisfaçam uma determinada condição ou quando precisa manipular a estrutura de forma otimizada. **Neste padrão, a coleção precisa estar ordenada.**

### Como funciona o padrão Two Pointers?

A ideia principal é usar dois ponteiros (ou índices) que percorrem a estrutura de dados em direções opostas ou na mesma direção, dependendo do problema. Esses ponteiros ajudam a reduzir a complexidade de tempo, muitas vezes de O(n2) para O(n), evitando a necessidade de loops aninhados.

### Quando usar o Two Pointers?

Esse padrão é útil em situações como:

1. **Problemas de busca em arrays ordenados** (ex.: encontrar dois números que somam um valor específico).
    
2. **Remover duplicatas em arrays ordenados**.
    
3. **Problemas de subsequências ou subarrays**.
    
4. **Manipulação de strings** (ex.: verificar se uma string é um palíndromo).

### Vantagens do Two Pointers:

1. **Eficiência:** Reduz a complexidade de tempo para O(n) em muitos casos.
    
2. **Simplicidade:** Evita a necessidade de estruturas de dados adicionais.
    
3. **Versatilidade:** Pode ser aplicado em diversos tipos de problemas.
    

### Desvantagens:

1. **Aplicabilidade limitada:** Funciona melhor em arrays ou listas ordenadas (ou que possam ser ordenadas).
    
2. **Dificuldade de adaptação:** Nem todos os problemas são resolvidos diretamente com essa técnica.

---

### Exemplo clássico: Encontrar dois números que somam um valor específico

Dado um array **ordenado** e um valor alvo, encontre dois números que somem esse valor.

#### Passos:

1. Inicialize dois ponteiros:
    
    - Um no início do array (`left`).
        
    - Outro no final do array (`right`).
        
2. Some os valores apontados pelos ponteiros:
    
    - Se a soma for igual ao valor alvo, retorne os índices.
        
    - Se a soma for menor que o valor alvo, mova o ponteiro `left` para a direita (aumentando a soma).
        
    - Se a soma for maior que o valor alvo, mova o ponteiro `right` para a esquerda (diminuindo a soma).
        
3. Repita até que os ponteiros se cruzem.


### Outro exemplo: Verificar se uma string é um palíndromo

Um palíndromo é uma string que é igual quando lida de trás para frente.

#### Passos:

1. Inicialize dois ponteiros:
    
    - Um no início da string (`left`).
        
    - Outro no final da string (`right`).
        
2. Compare os caracteres apontados pelos ponteiros:
    
    - Se forem iguais, mova ambos os ponteiros em direção ao centro.
        
    - Se forem diferentes, a string não é um palíndromo.
        
3. Repita até que os ponteiros se cruzem.

---
## References

**EDUCATIVE.IO.** Grokking the Coding Interview: Patterns for Coding Questions. **Educative.io,** [s.d.]. Disponível em: [https://www.educative.io/courses/grokking-coding-interview](https://www.educative.io/courses/grokking-coding-interview). Acesso em: 26  jan. 2025.

**ABDUL, Chanda.** Pattern 02: Two Pointers. **GitHub,** [s.d.]. Disponível em: [https://github.com/Chanda-Abdul/Several-Coding-Patterns-for-Solving-Data-Structures-and-Algorithms-Problems-during-Interviews/blob/main/%E2%9C%85%20%20Pattern%2002:%20Two%20Pointers.md](https://github.com/Chanda-Abdul/Several-Coding-Patterns-for-Solving-Data-Structures-and-Algorithms-Problems-during-Interviews/blob/main/%E2%9C%85%20%20Pattern%2002:%20Two%20Pointers.md). Acesso em: 26  jan. 2025.