---
Criado: 2025-05-27T16:37
Atualizado: 2025-05-27T16:37
Estudado: 2025-05-27T16:37
Links:
  - "[[Sistemas de Coordenadas para Grids Hexagonais]]"
---
---
# Sistema de coordenadas Cube

O sistema de **Coordenadas Cube** é uma das abordagens para identificar hexágonos em um grid hexagonal. Ele se destaca por sua **simetria elegante** e é frequentemente considerado o sistema **mais elegante para algoritmos**.

### Definição e Características:

*   Baseia-se em **três eixos primários**, em contraste com os dois eixos usados em grids quadrados.
*   A característica fundamental deste sistema é a **restrição** de que a soma das três coordenadas deve ser sempre zero: **q + r + s = 0**. Esta propriedade permite derivar uma coordenada a partir das outras duas.
*   Suporta diretamente **operações vetoriais padrão** como adição, subtração e escala. Esta é uma **vantagem significativa** sobre sistemas como Offset, que não permitem essas operações de forma segura diretamente nas coordenadas. Algoritmos que envolvem vetores se tornam mais simples.

### Relação com o Sistema Axial:

*   O sistema de **Coordenadas Axial (q, r)** é **essencialmente o mesmo** que o sistema Cube. A única diferença é que a coordenada 's' não é explicitamente armazenada no sistema Axial, sendo calculada como `s = -q - r` quando necessário.
*   Ambos os sistemas, Axial e Cube, suportam operações vetoriais e simplificam muitos algoritmos em comparação com o sistema Offset.

### Quando Usar Coordenadas Cube:

*   São **recomendadas** para mapas que podem ter **rotação** de hexágonos ou para mapas com **formas não retangulares**.
*   São a escolha preferencial para a **implementação de algoritmos**.

### Algoritmos Simplificados pelo Sistema Cube

Devido à sua estrutura e suporte a operações vetoriais, muitos algoritmos são mais fáceis ou mais elegantes de implementar usando Coordenadas Cube (ou Axial):

*   **Cálculo de Vizinhos:** É mais simples com Cube (e Axial/Doubled) do que com Offset.
*   **Cálculo de Distância:** A distância em um grid hexagonal usando coordenadas Cube é derivada da distância de Manhattan em 3D (com os eixos q, r, s) e dividida por dois, ou equivalentemente, é o máximo do valor absoluto das diferenças entre as coordenadas. A distância Axial é derivada da distância Cube.
*   **Cálculo de Alcance (Range):** Encontrar hexágonos a uma certa distância N de um centro é direto usando desigualdades baseadas nas coordenadas Cube/Axial. Interseccionar múltiplos alcances também é direto algebricamente usando as restrições q, r, s.
*   **Rotação e Reflexão:** São operações simples com Coordenadas Cube, envolvendo permutações e/ou negações das coordenadas, geralmente aplicadas a um vetor (deslocamento) a partir de um centro de rotação/reflexão.
*   **Desenho de Anéis e Espirais:** Algoritmos para gerar anéis ou espirais de hexágonos funcionam bem com operações de escala e adição de Coordenadas Cube (ou Axial/Doubled).
*   **Arredondamento:** Existe um algoritmo específico para arredondar coordenadas Cube de ponto flutuante para coordenadas inteiras, garantindo que a restrição q+r+s=0 seja mantida. Isso é útil na conversão de pixel para hex.
*   **Mapas Circulares (Wraparound):** Para mapas hexagonais, Coordenadas Cube podem ser usadas para identificar "centros espelho" que mapeiam hexágonos fora da borda de volta para o mapa principal.
*   **Pathfinding:** Embora o pathfinding use algoritmos genéricos (A*, Dijkstra), as funções de vizinhos e a heurística de distância são implementadas usando as propriedades do sistema de coordenadas escolhido, onde a distância Cube/Axial é a heurística adequada.

### Histórico

O sistema de coordenadas Cube foi visto pela primeira vez pelo autor do texto em uma postagem de Charles Fu em 1994. É por vezes referido como "R3 coordinates" .

Embora outros sistemas como Offset ou Doubled possam ser mais intuitivos para armazenamento de mapas retangulares (e Doubled facilita mais algoritmos que Offset), a capacidade do sistema Cube (e Axial) de lidar com operações vetoriais e sua simetria o tornam a escolha preferencial para a maioria dos algoritmos complexos em grids hexagonais. É comum converter entre sistemas quando necessário.

---
## References


PATEL, Amit. _Hexagonal Grids_. Red Blob Games, 2015. Disponível em: [https://www.redblobgames.com/grids/hexagons/](https://www.redblobgames.com/grids/hexagons/). Acesso em: 27 maio 2025.