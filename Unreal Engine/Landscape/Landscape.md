Ferramenta utilizada para criar terrenos outdoor de grandes dimensões e que possuem performance otimizada.

Possui três modos:
- **Sculpt:** usado para esculpir o landscape.
- **Manage:** para gerenciar seu landscape.
- **Paint:** para pintar seu landscape com materials.


## Criando um Landscape Material

Landscape Material é um tipo de Material usado para pintar seu landscape. Para cria-lo basta criar um Material e adiciona o node "Landscape Layer Blend" e conectar as texturas e os normal maps (como na imagem abaixo). Após criado, adicione o Material ao seu landscape e isso possibilitará que as diferentes texturas sejam usadas no modo "paint".

![[landscapeMaterial.png]]

## Layer info object

Deve ser criado para cada textura usada no landscape material. Podem ser de dois tipos:

### Weight-Blended Layer (normal)

Quando pintado sobre outro layer irá misturar os layers. Por exemplo misturar dois tipos de terrenos como areia ou terra.

### Non Weight-Blended Layer

Quando pintado sobre outro layer NÃO irá misturar os layers e sim empilhar um sobre o outro. Útil por exemplo quando deseja efeitos de neve que deve ficar por cima da terra.
