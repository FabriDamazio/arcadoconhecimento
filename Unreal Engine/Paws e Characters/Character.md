Estende a classe [[Pawn]] com alguns componentes para representar um jogador que possa andar, pular, nadar, correr, etc (que tenha o movimento orientado verticalmente).

Os seguintes componentes são adicionados:

- _SkeletalMeshComponent:_ possibilita animações avançadas que usam skeleton.
- _CapsuleComponent:_ usado para colisão de movimento. É uma capsula orientada verticalmente.
- _CharacterMovementComponent:_ possibilita que avatares que não usam rigid body physics  a se moverem, pularem, etc. É específico a classe Character e não pode ser implementada por outra classe. Inclui valores de fricção, movimento pelo ar e água, etc.

