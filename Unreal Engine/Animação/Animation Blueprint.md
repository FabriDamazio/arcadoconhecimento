Animation Blueprints são Blueprints especializados que controlam a animação de uma Skeletal Mesh durante o jogo. No AnimGraph podemos mesclar animações, controlar os bones de um Skeleton ou criar uma lógica que definirá a pose final da animação para uma Skeletal Mesh frame a frame

## Atribuindo a um Character

O Animation Blueprint deve ser atribuído ao character para ter efeito. Para fazer isso deve mudar as seguintes propriedades:

- **Animation Mode** para o valor **Use Animation Blueprint**.
- **Anim Class** para o seu blueprint de animação.

## Animation Blueprint Editor

No editor temos acesso a diversas opções e propriedades. As mais importantes são:

### AnimGraph

É onde construímos as lógicas baseadas nas poses do character que serão avaliadas para chegar na pose final daquele frame. Podemos usar State Machines, [[IK Rig]] e outras lógicas como no exemplo abaixo:
![[AnimGraph.png]]

### State machines

Dentro do AnimGraph podemos criar **State Machines** para construir a lógica necessária para a locomoção. Nele criamos States (que estão ligadas a uma pose), conectamos uma State ao outro e definimos condições para que sejam avaliadas.

**Geralmente usamos para animações "constantes" (em loop) como idle, walking, run, etc. Para outras animações como ataque, etc utilizamos [[Animation Montage]].**

No exemplo abaixo estamos conectando o State Idle com o Run. A bolinha branca representa uma lógica para ser avaliada:
![[StateMachine1.png]]

Ao abrir a bolinha branca temos visão da condição:
![[StateMachineCondition.png]]

As State Machines podem ser salvas em cache para serem usadas na lógica do AnimGraph:
![[StateMachineCache.png]]