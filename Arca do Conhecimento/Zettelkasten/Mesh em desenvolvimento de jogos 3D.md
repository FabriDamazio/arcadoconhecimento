---
Criado: 2025-06-14T11:36
Atualizado: 2025-06-14T11:36
Estudado: 2025-07-30T17:09
Links:
  - "[[Modelagem 3D em Jogos Digitais]]"
tags:
  - gamedev
---
---
# Mesh em desenvolvimento de jogos 3D

Uma **Mesh** (malha) ou **Polygon mesh** (malha poligonal) é uma coleção de vértices, arestas e faces que definem a forma de um objeto tridimensional em um espaço 3D. Ela representa a geometria do objeto, descrevendo sua estrutura física, mas não inclui informações sobre textura, cor ou material.

## Estrutura Básica de uma Mesh

- **Vértices (Vertices)**: Pontos no espaço 3D com coordenadas (x, y, z).
- **Arestas (Edges)**: Linhas que conectam dois vértices.
- **Faces (Faces ou Polígonos)**: Superfícies planas definidas por três ou mais vértices (em geral, triângulos).    

---

## Tipos de Mesh Comuns

- **Static Mesh**: Malha estática, que não sofre deformações (ex.: cenários, objetos inanimados).
- **Skeletal Mesh**: Malha com esqueleto interno para animação (ex.: personagens, criaturas).
- **Procedural Mesh**: Malha gerada ou alterada em tempo de execução (ex.: terrenos dinâmicos, destruição procedural).

## Relação com Outros Conceitos

- **Material**: Define a aparência da Mesh (ex.: cor, textura, shader).
- **Collider**: Muitas vezes, uma Mesh é usada para gerar colisões, mas é comum usar versões simplificadas para desempenho.
- **LOD (Level of Detail)**: Uso de diferentes versões de Mesh com níveis variados de detalhes para otimizar performance.

---
## References

WIKIPÉDIA. **Polygon mesh**. Disponível em: [https://en.wikipedia.org/wiki/Polygon_mesh](https://en.wikipedia.org/wiki/Polygon_mesh). Acesso em: 14 jun. 2025.