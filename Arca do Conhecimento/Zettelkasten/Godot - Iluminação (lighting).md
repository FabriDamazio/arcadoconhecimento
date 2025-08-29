---
Criado: 2025-06-22T17:07
Atualizado: 2025-06-22T17:07
Estudado: 2025-08-29T09:34:00
Links:
  - "[[Godot Engine]]"
  - "[[Iluminação em jogos digitais]]"
---
---
# Godot - Iluminação (lighting)

Existem diversos tipos de fontes de luz em uma cena na Godot. Pode ser do próprio material (na forma de emission color), de nodes de iluminação, luzes de ambiente (environment) e iluminação global.

Luzes podem opcionalmente projetar sombras que podem ter seus parâmetros ajustados conforme necessário.

---
## Tipos de Nodes de iluminação

### DirectionalLight3D

Node que representa uma fonte de luz direcional que ilumina a cena uniformemente de uma direção. Não se altera com a distância ou escala de cena. Representa fontes de luz que estão muito longe como o sol.
### OmniLight3D

Node que representa uma fonte de luz "point" que emite um único ponto de luz para todas as direções e perde a intensidade de acordo com a distância. Um exemplo é a luz de uma lâmpada.

Dica: a propriedade `attenuation` de valor 2.0 é fisicamente correta.
### SpotLight3D

Node que representa uma fonte de luz focal que projeta um cone de luz que perde a intensidade de acordo com a distância. Um exemplo é a luz de uma lanterna.

---
## Environment (ambiente)

É o recurso que armazena todas as informação necessárias para o controle de rederização 2D e 3D. Inclui informações como tone mapping, ambient lighting e sky.

Um environment pode ser adicionado a uma cena ou câmera. Quando adicionado na câmera ativa ela sobrescreve o environment do ambiente.

Caso a cena não tenha um environment, o editor adiciona um automaticamente na tela de preview da cena para que a tela não fique completamente escura.


---
## References

GODOT ENGINE. _Environment and post-processing_. Disponível em: [https://docs.godotengine.org/en/stable/tutorials/3d/environment_and_post_processing.html](https://docs.godotengine.org/en/stable/tutorials/3d/environment_and_post_processing.html). Acesso em: 22 jun. 2025.

GODOT ENGINE. _Lights and shadows_. Disponível em: [https://docs.godotengine.org/en/stable/tutorials/3d/lights_and_shadows.html](https://docs.godotengine.org/en/stable/tutorials/3d/lights_and_shadows.html). Acesso em: 22 jun. 2025.