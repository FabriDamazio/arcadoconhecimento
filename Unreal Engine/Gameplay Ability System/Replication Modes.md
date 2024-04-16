O `ASC` define três modos para replicar os `GameplayEffects`, `GameplayTags`, and `GameplayCues` - `Full`, `Mixed`, e `Minimal`. Já os `Attributes` são replicados pelo seu `AttributeSet`.

|Modo |Quando usar |Descrição |
|---|---|---|
|`Full`|Single Player|Every `GameplayEffect` is replicated to every client.|
|`Mixed`|Multiplayer, player controlled `Actors`|`GameplayEffects` are only replicated to the owning client. Only `GameplayTags` and `GameplayCues` are replicated to everyone.|
|`Minimal`|Multiplayer, AI controlled `Actors`|`GameplayEffects` are never replicated to anyone. Only `GameplayTags` and `GameplayCues` are replicated to everyone.|

**Importante:** no modo `Mixed`, é esperado que o `OwnerActor's` `Owner` seja o `Controller`. `PlayerState's` `Owner` é o `Controller` por padrão mas o `Character's` não é. Se usar o modo de replicação `Mixed` com o  `OwnerActor` não sendo o  `PlayerState`, então você precisa chamar a função `SetOwner()` do `OwnerActor` com um controller válido `Controller`.