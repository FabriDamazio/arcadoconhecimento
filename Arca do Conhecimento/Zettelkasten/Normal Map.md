---
Criado: 2025-06-14T15:20
Atualizado: 2025-06-14T15:20
Estudado: 2025-07-30T17:13
Links:
  - "[[Texturas em jogos 3D]]"
  - "[[Godot - Material]]"
tags:
  - gamedev
---
---
# Normal Map

Um Normal Map é uma textura especial que armazena informações sobre a orientação das superfícies de uma Mesh, simulando detalhes geométricos complexos sem a necessidade de aumentar o número de polígonos.

Ele altera a forma como a luz interage com a superfície, criando a ilusão de relevo, sulcos ou saliências, mesmo que a geometria real permaneça plana.

## Como funciona

Cada pixel do Normal Map contém um vetor tridimensional codificado em cores RGB, representando a direção da "normal simulada" naquele ponto da superfície.

- Cor Azulada: Normal apontando para fora da superfície (orientação padrão).
- Variações em Verde e Vermelho: Desvios laterais na orientação da normal.

### Normal Map e PBR

No contexto de PBR (Renderização Baseada em Física), o Normal Map é essencial para adicionar microdetalhes visuais, como:

- Rugosidade de uma parede.
- Ranhuras em metais.
- Relevo de tijolos ou pedras.

Ele funciona em conjunto com mapas como Albedo, Metallic, Roughness, entre outros.

### Diferença entre OpenGL e DirectX nos Normal Maps

Uma diferença importante ao trabalhar com Normal Maps é a forma como o eixo Y (Green Channel) é interpretado nas duas APIs gráficas mais comuns:

| API / Engine Base             | Direção do eixo Y (canal verde) no Normal Map |
|-------------------------------|-----------------------------------------------|
| **OpenGL (Godot, Unreal, etc.)** | Y positivo aponta **para cima**              |
| **DirectX (Unity, jogos Windows antigos)** | Y positivo aponta **para baixo**       |

Se você usar um **Normal Map gerado para DirectX** dentro de uma engine que segue o padrão **OpenGL** (como a Godot), os detalhes de relevo podem parecer **invertidos**, com áreas que deveriam ser saliências parecendo reentrâncias (e vice-versa).

Soluções possíveis:

- **Reexportar o Normal Map** com a orientação correta durante o bake ou exportação.
- **Inverter o canal verde (Y)** manualmente usando um editor de imagem ou ferramenta de texturização.
- Usar as opções de **flip Y** (quando disponíveis) dentro da engine de jogo durante a importação da textura.

---
## References

WIKIPÉDIA. **Normal mapping**. Disponível em: [https://en.wikipedia.org/wiki/Normal_mapping](https://en.wikipedia.org/wiki/Normal_mapping). Acesso em: 14 jun. 2025.

GODOT ENGINE. **Using normal maps — Godot Engine (stable documentation)**. Disponível em: https://docs.godotengine.org/en/stable/tutorials/assets_pipeline/normal_maps.html. Acesso em: 14 jun. 2025.