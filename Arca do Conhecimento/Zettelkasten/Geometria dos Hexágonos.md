---
Criado: 2025-05-28T10:09
Atualizado: 2025-05-28T10:09
Estudado: 2025-07-16T13:38
Links:
  - "[[Sistemas de Coordenadas para Grids Hexagonais]]"
---
---
# Geometria dos Hexágonos

Hexágonos regulares são polígonos com seis lados iguais, usados frequentemente em mapas de grade em jogos. Seu comportamento geométrico influencia diretamente o espaçamento e a renderização em engines de jogos. 

## Dimensões e espaçamento

Um hexágono regular pode ser definido pelo raio do círculo externo ("size", que vai até os vértices) e pelo raio do círculo interno (que toca os lados).

A largura (`width`) e altura (`height`) dependem do dobro desses raios:
- `width = sqrt(3) * size`
- `height = 2 * size`   

Existem duas **orientações possíveis**: com vértices para cima (_pointy top_) ou com lados para cima (_flat top_). 

![[hex1.png]]

Quando colocamos vários hexágonos juntos, o cálculo do espaçamento entre eles depende do raio do círculo externo e do raio do círculo interno.

**Orientação com vértices para cima (pointy top)**:
- `espaçamento horizontal = 3/2 * size` 
- `espaçamento vertical = sqrt(3) * size`

![[hex2.png]]

**Orientação com lados para cima (flat top)**:
- `espaçamento horizontal = sqrt(3) * size`
- `espaçamento vertical = 3/2 * size`

![[hex3.png]]

## Ângulos

Em um hexágono regular, os ângulos internos são de 120°. Existem seis "fatias", cada uma sendo um triângulo equilátero com ângulos internos de 60°. Cada vértice está a uma distância de **size** unidades do centro.

![[hex4.png]]


---
## References


PATEL, Amit. _Hexagonal Grids_. Red Blob Games, 2015. Disponível em: [https://www.redblobgames.com/grids/hexagons/](https://www.redblobgames.com/grids/hexagons/). Acesso em: 27 maio 2025.