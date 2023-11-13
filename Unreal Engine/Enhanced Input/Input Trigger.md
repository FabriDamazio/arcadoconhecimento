São condições que determinam se o input do usuário deve ativar ou nao a [[Input Action]] correspondente.

Existem três tipos:

- **Explicit:** faz o input ter sucesso se ele for ativado.
    
- **Implicit:** o input tem sucesso somente se ele e todos outros implicit forem ativados.
    
- **Blocker:** faz o input falhar caso ativado.

Depois de processar o input os triggers podem retornar um dos três estados:

- **None:** indica que as condições não foram atingidas então ele falhou.
    
- **Ongoing:** indica que as condições estão parcialmente atingidas mas ainda não teve sucesso.
    
- **Triggered:** indica que todas condições foram atingidas com sucesso.