---
Criado: 2025-08-12T14:58
Atualizado: 2025-08-12T14:58
Estudado: 2025-08-12T14:58
Links:
  - "[[Elixir - Tipos de dados]]"
---
---
# Elixir - Charlist

Charlist é uma `List` de inteiros onde todos eles representam um código Unicode (code points) válido. Ele é escrito com aspas simples (por exemplo `'abc'`) e é diferente de strings que são escritas com aspas duplas.

Na prática ela é usada em casos específicos para fazer interface com antigas bibliotecas Erlang que não aceitam binários como argumentos.

O sigil `~c` indica que estamos lidando com um charlist e não uma string.

```elixir
# criando uma charlist usando o sigil
~c"hello"
# criando a mesma charlist sem sigil
[?h, ?e, ?l, ?l, ?o]

```

## Códigos Unicode (Code Points)

O **Padrão Unicode** serve como um registro oficial de praticamente todos os caracteres que conhecemos — incluindo caracteres de textos clássicos e históricos, emojis, caracteres de formatação e controle.

O Unicode organiza todos esses caracteres em **tabelas de códigos**, e cada um recebe um **índice numérico único**, chamado de **Code Point**.

No Elixir, você pode usar um **`?` antes de um caractere** para ver seu **Code Point**:

```elixir
?a   #=> 97   (código Unicode para 'a')
?á   #=> 225  (código Unicode para 'á' com acento)
?🔥  #=> 128293 (código Unicode para o emoji de fogo)
```

---
## References

ELIXIR. **Binaries, strings, and charlists**. [S. l.], 2024. Disponível em: <https://hexdocs.pm/elixir/binaries-strings-and-charlists.html>. Acesso em: 12 aug. 2026.  