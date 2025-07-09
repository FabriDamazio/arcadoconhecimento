---
Criado: 2025-05-27T16:06
Atualizado: 2025-05-27T16:06
Estudado: 2025-07-09T09:56
Links:
  - "[[Sistemas de Coordenadas em Jogos]]"
---
---
# Sistemas de Coordenadas para Grids Hexagonais

Ao trabalhar com grids hexagonais, é necessário escolher um **sistema de coordenadas** para identificar cada hexágono. Diferentemente dos grids quadrados, existem **múltiplas abordagens** para fazer isso. A escolha do sistema impacta como você implementará algoritmos (como cálculo de vizinhos ou distâncias) e como armazenará os dados do mapa.

Os principais sistemas de coordenadas mencionados são:

*   **Coordenadas Offset (col, row):** Este é o sistema **mais comum**. Funciona deslocando alternadamente as linhas ou colunas. Uma desvantagem é que **não suporta diretamente operações vetoriais** como soma e subtração de coordenadas, tornando alguns algoritmos mais complexos, pois o cálculo de vizinhos, por exemplo, depende da paridade da linha/coluna. É frequentemente usado para mapas retangulares.
*   **Coordenadas Doubled (col, row):** Uma alternativa ao sistema Offset, também para mapas retangulares. Em vez de deslocar, este sistema "dobra" o tamanho do passo em uma direção. Diferentemente do Offset, os **vizinhos não dependem da localização**, e você **pode somar e subtrair** coordenadas doubled de forma segura, facilitando alguns algoritmos comparado ao Offset. Possui fórmulas diretas para distâncias.
*   **Coordenadas Axial (q, r):** Essencialmente **o mesmo sistema que o Cube**, mas a terceira coordenada (s) não é armazenada explicitamente. Como no sistema Cube, **suporta operações vetoriais**. É recomendado para mapas não retangulares ou que podem ser rotacionados.
*   **Coordenadas Cube (q, r, s):** Baseado em **três eixos** com a restrição **q + r + s = 0**. É considerado o sistema **mais elegante para algoritmos** devido à sua simetria e por **suportar operações vetoriais padrão**. Também é recomendado para mapas não retangulares ou com rotação. Muitos algoritmos de distância, alcance e rotação são mais simples neste sistema.

É comum e muitas vezes necessário **converter** entre esses sistemas, especialmente para usar algoritmos que são mais simples em Axial/Cube a partir de coordenadas Offset ou Doubled.

Em resumo, enquanto Offset é comum e Doubled é uma alternativa melhor para mapas retangulares sem rotação, **Axial e Cube** são frequentemente preferidos para a implementação de algoritmos complexos devido à sua compatibilidade com operações vetoriais e simetria inerente.

Cada um desses sistemas possui detalhes específicos sobre como calcular vizinhos, distâncias e como converter para coordenadas de tela

---
## References

PATEL, Amit. _Hexagonal Grids_. Red Blob Games, 2015. Disponível em: [https://www.redblobgames.com/grids/hexagons/](https://www.redblobgames.com/grids/hexagons/). Acesso em: 27 maio 2025.