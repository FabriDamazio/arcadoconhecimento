**Collision Responses** e **Trace Responses** foram a base de como a engine lida com colisão.

## Collision Responses

Cada objeto que pode colidir ganha um tipo chamado de **Object Type**. Com base nesse tipo é possível configurar a colisão com os outros tipos.

## Trace Responses

Funcionam basicamente da mesma maneira, exceto que o próprio trace (ray cast) pode ser definido como um dos tipos de resposta de trace, permitindo assim que os atores o bloqueiem ou ignorem com base em suas respostas de trace.

## Presets de colisão

Quando o objeto pode colidir, temos a opção de ligar, desligar e configurar a colisão. A Engine já oferece vários presets prontos ou podemos personaliza-los.

Spatial queries (raycasts, trace, overlap) são usados para calcularmos distâncias (line tracers) e utilizar como por exemplo no IK (inverse kinematics). Serve de forma geral para bloquear movimentação.

Já simulation (rigid body, constraints) tem o propósito de aplicar e realizar simulações de física da engine de física.

Para ligar e desligar temos as seguintes opções:

- **No Collision** → Este corpo não terá representação na engine de física. Não pode ser usado para spatial queries ou simulation. Esta configuração oferece o melhor desempenho possível, especialmente para objetos em movimento.

- **Query Only** → Este corpo é usado apenas para spatial queries. Não pode ser utilizado para simulation. Esta configuração é útil para movimentos de personagens e objetos que não necessitam de simulação física. Alguns ganhos de desempenho são obtidos com a redução dos dados na árvore de simulação física.

- **Physics Only** → Este corpo é apenas para simulation (simulação de física). Não pode ser usado para spatial queries. Esta configuração é útil para movimentos secundários simulados em personagens que não precisam de detecção por bone. Alguns ganhos de desempenho são obtidos com a redução dos dados na árvore de consulta.

- **Collision Enabled** → Este corpo pode ser usado tanto para spatial queries quanto para simulation.

Visão geral do painel de Collision Presets do objeto:
![[collision_response.png]]

