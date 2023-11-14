Pawn é a classe base para todos os Actors que podem ser controlados por jogadores ou AI. Ela é a representação física do Actor no mundo e determina seu visual, localização, colisão e outras interações físicas.

**Por padrão existe um relacionamento de um pra um entre Controllers e Paws, o que significa que um Controller pode controlar apenas um Pawn de cada vez.**

A classe padrão contem os seguintes componentes:

- _DefaultPawnMovementComponent:_ movimento básico com aceleração, velocidade e desaceleração.
- _CollisionComponent:_ uma colisão esférica padrão.
- _StaticMeshComponent:_ uma mesh para representar o Pawn no mundo.