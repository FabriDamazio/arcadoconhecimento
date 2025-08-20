---
Criado: 2024-12-27T20:14
Atualizado: 2025-06-04T10:48
Estudado: 2025-08-20T11:57:00
Links:
  - "[[Elixir language]]"
  - "[[Elixir - AST  (Abstract Syntax Tree)]]"
  - "[[Macro]]"
---
---
# Metaprogramming em Elixir

Metaprogramação é o processo de escrever código que gera ou modifica outros códigos. Em Elixir isto acontece através da manipulação da **AST  (Abstract Syntax Tree)**, permitindo a alteração do comportamento do programa em tempo de compilação.

## **Ferramentas de Metaprogramação em Elixir**:

  -  **Macros**: Criam ou transformam código em tempo de compilação.
  -  **Quote e Unquote**: Manipulam diretamente a AST:
  - `quote`: Converte o código para sua representação AST.
  - `unquote`: Injeta código dentro de uma AST.
  -  **Code.string_to_quoted/1**: Converte uma string com código para AST.
  -  **Macro.to_string/1**: Converte uma AST para código legível.

### **Macros vs Funções**:  

Macros operam em tempo de compilação, enquanto funções são avaliadas em tempo de execução.

### **Casos de Uso Comuns**:

   - Criar DSLs (Domain-Specific Languages).
   - Automatizar tarefas repetitivas, como definir rotas em frameworks.
   - Manipular comportamento padrão de módulos ou funções.

---
## References

**ELIXIR SCHOOL.** _Metaprogramming._ Disponível em: [https://elixirschool.com/en/lessons/advanced/metaprogramming](https://elixirschool.com/en/lessons/advanced/metaprogramming). Acesso em: 22 dez. 2024.