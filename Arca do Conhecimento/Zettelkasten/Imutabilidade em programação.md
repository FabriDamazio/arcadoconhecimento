---
Criado: 2025-06-02T10:19
Atualizado: 2025-06-02T10:19
Estudado: 2025-08-13T11:09
Links:
  - "[[Programação de computadores]]"
  - "[[Paradigma funcional de programação]]"
  - "[[Rust language]]"
  - "[[Elixir language]]"
tags:
  - programação
---
---
# Imutabilidade em programação

Imutabilidade é a propriedade de um valor ou estrutura de dados que, uma vez criado, não pode ser alterado. Na linguagem Elixir, por exemplo, os dados são imutáveis. Já na linguagem Rust eles são imutáveis por padrão mas podem ser mudados para mutáveis quando desejado. 

## Benefícios

- **Evita efeitos colaterais**: Como os dados não mudam, funções que operam sobre eles não têm impacto externo.
- **Facilita o paralelismo e concorrência**: Sem alterações de estado, múltiplas threads podem acessar os dados sem conflitos.
- **Torna o código mais previsível**: Comportamento de funções é mais fácil de entender e testar.

---
## References

WIKIPEDIA. _Immutable object_. Wikipédia, a enciclopédia livre. Disponível em: [https://en.wikipedia.org/wiki/Immutable_object](https://en.wikipedia.org/wiki/Immutable_object). Acesso em: 2 jun. 2025.