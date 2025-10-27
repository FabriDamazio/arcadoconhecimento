---
Criado: 2025-06-14T11:44
Atualizado: 2025-06-14T11:44
Estudado: 2025-07-30T17:10
Links:
  - "[[Mesh em desenvolvimento de jogos 3D]]"
  - "[[Texturas em jogos 3D]]"
tags:
  - gamedev
---
---
# UV Mapping

UV Mapping é o processo de projetar uma imagem 2D (textura) sobre a superfície de uma Mesh 3D. Ele define como cada ponto da malha (vértices) corresponde a coordenadas na textura.

## Conceitos Básicos

- **Coordenadas UV**: Sistema de coordenadas bidimensional (U e V) usado para mapear texturas. U representa o eixo horizontal, V o vertical, ambos relativos à textura.
- **Seam (Costura)**: Linha onde a malha é "cortada" para ser desdobrada em 2D.
- **Unwrapping (Desdobramento)**: Processo de abrir a malha 3D em um layout 2D para aplicar a textura.

## Exemplo de Aplicação

Se uma Mesh representa um personagem, o UV Mapping determina onde os olhos, a boca e as roupas aparecem na textura 2D quando aplicadas sobre a malha.

## Importância para Jogos Digitais

- Permite aplicar texturas detalhadas sem necessidade de criar geometria complexa.
- Essencial para efeitos de normal mapping, specular maps e outras técnicas de sombreamento.
- Otimiza a memória, pois a mesma textura pode ser aplicada em múltiplas instâncias de uma Mesh.

---
## References

WIKIPÉDIA. **UV mapping**. Disponível em: [https://en.wikipedia.org/wiki/UV_mapping](https://en.wikipedia.org/wiki/UV_mapping). Acesso em: 14 jun. 2025.