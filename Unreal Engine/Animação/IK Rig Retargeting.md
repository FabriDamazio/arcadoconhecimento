IK Rigs podem ser usados para criar retargeting de animação entre diferentes Skeletal Meshes. É possível transferir animação entre skeletons com números variados de bones que possuem nomes e orientações diferentes.

Para fazer o retargeting de duas Skeleton Mashes diferentes é preciso criar um Blueprint _IK Retargeter_

## IK Retargeter
  
Para criar um IK Retargeter, clique em Adicionar (+) no Content Browser e selecione _Animation > IK Rig > IK Retargeter_. O próximo passo é definir qual será o Skeleton Mesh e o IK Rig seráo o source e o target.

### Retarged Chains

São uma cadeia de bones que possuem um bone inicial e um final. Por exemplo, uma cadeia pode ser formada pelo bone do ombro até o antebraço.

**Os Retarged Chains devem ser criados nos Blueprints de IK Rigs do source e do target e é uma boa prática ter o mesmo nome tanto no source quanto no target para facilitar o mapeamento.**

Exemplo de criação de um chain dos bones da espinha dorsal que contém três bones e o nome _Spine_. Basta seleciona a cadeia e clicar com o botão direito para abrir a opção de criação:
![[chainspine.png]]

O Chain irá aparecer com suas informações de nome, bone inicial e bone final:
![[chainspine2.png]]

### Retarget Root
  
Além de definir chains, você também deve definir o Retarget Root, que normalmente é a pélvis ou o osso do quadril. Isto é feito para que o movimento raiz do personagem possa ser definido e transferido de forma proporcional.

Para definir o Retarget Root basta selecionar o bone e clicar com o botão direito para abrir a opção.

## Retarged Pose

No Blueprint de IK Retargeter pode ser necessário editar a pose padrão caso ela esteja diferente para aumentar a precisão do retargeting. 

Exemplo de poses diferentes:
![[retargetingpose.png]]

Após criar as chains no source e no target devemos então fazer o mapeamento (correlação) delas entre o source e o target:
![[chainmapping.png]]


## Animation Import e Export

Terminado o processo basta verificar como ficaram as animações desejadas e exporta-las:
![[exportanimations.png]]
