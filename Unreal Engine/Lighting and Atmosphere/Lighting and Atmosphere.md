A iluminação e atmosfera pode ser formada pelos 5 elementos a seguir:

## Sky Atmosphere

Cria uma atmosfera parecida com a do planeta terra. Ela "espalha" a luz simulando um atmosfera real. Suporta até duas luzes atmosféricas.
## Directional Light

É um ponto de luz que fica "infinitamente" longe. As sombras que ela projeta são todas em paralelo. Este tipo de luz é usado para simular corpos celestes luminosos como sol e lua. Uma de sua característica mais importante esta relacionada com a propriedade Mobility que suporta os seguintes modos:

- **Static:** luz não pode ser alterada in-game, é rápida e permite baked lighting.
- **Stationary:** color e intensidade podem ser alteradas in-game e permite baked lighting parcial.
- **Movable:** pode ser alterada e movida in-game, é a que requer maior processamento e permite sombras dinâmicas.

## Sky Light

Ela "captura" a informação de iluminação de partes distantes do seu level e aplica na cena em forma de iluminação (reflexos). É dessa forma que temos o efeito de iluminação global. Essa "captura" ocorre da seguinte forma:
- Para luzes estáticas (static), na hora do build da iluminação.
- Para luzes stationary e movable, no carregamento e se você dispara isso manualmente.
- Se a opção de captura Real-Time estiver ligada, ela ocorre constantemente.

## Exponential Height Fog

Usada pra simular névoa/neblina. Simula ela de acordo com a altura do chão, sendo quanto mais baixo você esta, mais fina ela fica (simulando pressão atmosférica). Possui duas cores, uma para o "hemisfério" do planeta de frente ao sol e outra para o "hemisfério" escuro.
## Volumetric Clouds

São nuvens dinâmicas tri-demensionais e que utilizam material que podem ser trocados. Elas também "espalham" as luzes assim como a atmosfera.