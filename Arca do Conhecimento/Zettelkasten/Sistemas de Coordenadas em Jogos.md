---
Criado: 2025-05-27T15:43
Atualizado: 2025-05-29T14:58
Estudado: 2025-05-27T15:43
Links:
  - "[[Game Design]]"
---
---
# Sistemas de Coordenadas em Jogos

Sistemas de coordenadas são fundamentais para representar posições, movimentos e colisões em jogos. A escolha do sistema impacta diretamente a lógica de movimentação, renderização e jogabilidade. Os principais tipos usados são: cartesiano, isométrico, polar e hexagonal.

## Sistema Cartesiano

- Usado em jogos 2D e 3D.
- Representa pontos com pares ou trios `(x, y)` ou `(x, y, z)`.
- Em 2D, a origem pode estar no canto superior esquerdo (*screen space*) ou no centro (*world space*).
- Padrão em motores como Unity, Godot e Unreal.

## Sistema Isométrico

- Simula 3D com gráficos 2D (falsa perspectiva).
- Utiliza uma projeção onde os eixos X e Y formam um ângulo de 120°.
- Conversão entre coordenadas cartesianas e isométricas é necessária para posicionamento e colisão.

## Sistema Hexagonal

- Usado em jogos de estratégia (ex: *Civilization*).
- Pode ser representado por: Coordenadas Offset, Doubled, Axial ou Cube.

---
## References

WIKIPÉDIA. Sistema de coordenadas. Wikipédia, a enciclopédia livre, 2024. Disponível em: https://pt.wikipedia.org/wiki/Sistema_de_coordenadas. Acesso em: 27 maio 2025.

PATEL, Amit. _Hexagonal Grids_. Red Blob Games, 2015. Disponível em: [https://www.redblobgames.com/grids/hexagons/](https://www.redblobgames.com/grids/hexagons/). Acesso em: 27 maio 2025.

WIKIPÉDIA. _Perspectiva isométrica_. Wikipédia, a enciclopédia livre, 2024. Disponível em: [https://pt.wikipedia.org/wiki/Perspectiva_isom%C3%A9trica](https://pt.wikipedia.org/wiki/Perspectiva_isom%C3%A9trica). Acesso em: 27 maio 2025.