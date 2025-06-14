---
Criado: 2025-06-14T12:33
Atualizado: 2025-06-14T12:33
Estudado: 2025-06-14T12:33
Links:
  - "[[UV Mapping]]"
---
---
# Texturas em jogos 3D

**Texturas** são imagens 2D. Podem ser aplicadas sobre a superfície de uma **Mesh** ([[Mesh em desenvolvimento de jogos 3D]]) para adicionar detalhes visuais como cor, relevo, brilho ou propriedades especiais, sem alterar a geometria da malha.

## Relação entre Textura, Mesh e UV Mapping

- A **Mesh** define a forma tridimensional do objeto.
- O **UV Mapping** determina como os pontos da malha (vértices) correspondem a regiões da textura.
- A **Textura** fornece os dados visuais (cores, relevo, etc.) que serão aplicados sobre a malha.

---
## Texturas e Materiais

Em uma engine de jogos, as texturas não são aplicadas diretamente na Mesh. Em vez disso, elas são atribuídas a um **Material**.

O **Material** é quem define o **comportamento visual completo** de uma superfície, incluindo:

- Quais texturas usar (ex.: cor, normal map, especular, etc.).
- Como essas texturas afetam a renderização (ex.: como interagem com a luz).
- Parâmetros adicionais como transparência, brilho e efeitos especiais.

A Mesh então recebe esse **Material**, e a engine usa as informações dele para renderizar o objeto.

---
## Exemplo Prático

Um personagem pode ter uma Mesh simples com poucos polígonos, mas com um **Material bem configurado** e **texturas detalhadas**, o resultado visual pode ser muito mais realista.

---
## References

WIKIPÉDIA. **Texture mapping**. Disponível em: [https://en.wikipedia.org/wiki/Texture_mapping](https://en.wikipedia.org/wiki/Texture_mapping). Acesso em: 14 jun. 2025.