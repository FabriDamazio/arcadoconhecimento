É um framework flexível para construir sistemas de habilidades e atributos encontrados em jogos como RPG ou MOBA. Por exemplo é possível construir habilidades ativas e passivas com efeitos que podem afetar um ou mais atributos, entre outros.

O sistema ajuda a organizar e gerenciar o relacionamento entre as habilidades e atributos que podem ficar complexo rapidamente.

## Principais partes do GAS

![[gascomponents.png]]

### 1. Ability System Component (ASC)

É o coração do GAS que manipula todas as interações com o sistema. Qualquer _Actor_ que deseja utilizar _GameplayAbilities_, _Attributes_, _GameplayEffects_ devem ter um _ASC_ acoplado a eles.

### 2. Attribute Set

É um conjunto que armazena e gerencia as mudanças nos _Attributes_. Um _Actor_ pode ter um ou mais _Attribute Set_ desde que não sejam da mesma classe.

### 3. Gameplay Ability (GA)

É qualquer ação ou habilidade que um ator pode fazer no jogo. Mais de um GA pode estar ativo ao mesmo tempo e podem ser feitos em blueprint ou C++;

### 4. Ability Tasks

_GameplayAbilities_ são executadas apenas em um frame. Para realizar ações que acontecem ao longo do tempo ou que exigem resposta em algum momento posterior, usamos _AbilityTasks_.

### 5. Gameplay Effect (GE)

É através de um GE que uma _Gameplay Ability_ modifica _Attributes_ e _Tags_. Elas os modificam através de _Modifiers_ e _Executions_ e podem ter três tipos de duração: _Instant_, _Duration_ e _Infinite_.

### 6. Gameplay Cues

Executam coisas não relacionadas ao gameplay como efeitos sonoros, partículas, balançar a camera, etc.

### 7. Gameplay Tags

```FGameplayTags``` são nomes hierárquicos no formato: ```Parent.Child.Grandchild...``` e que são registrados no ```GameplayTagManager```. Essas tags são extremamente úteis para classificar e descrever o estado de um objeto. Por exemplo, se um personagem estiver atordoado, poderíamos atribuir a ele uma ```GameplayTag State.Debuff.Stun``` durante o atordoamento.


## Quando usar Player State

Geralmente para players criamos um ```player state``` para que possam ser acoplados o Ability System Component e seus Attributes Sets. Ao não conectar direto a um Pawn nos permite trocar o Pawn caso preciso e não perder os Attributes caso o Pawn seja destruído.

Já para inimigos podemos usar um player state mas caso ele seja simples o ASC e Attribute sets podem ser acoplados diretos a seu Pawn.

![[gasplayerstates.png]]