É o novo sistema de input introduzido na Unreal Engine 5 que permite funcionalidades mais avançadas e complexas para o sistema de input.

## Adicionando ao seu projeto

Para adicionar ao seu projeto você deve verificar se o plugin do Enhanced Input esta ativo nos plugins da Unreal Engine no menu Edit->Plugins.

Depois deve adicionar ao seu arquivo .Build do codigo a dependência do módulo:

```cpp
PublicDependencyModuleNames.AddRange(new string[] { "Core", "CoreUObject", "Engine", "InputCore", "EnhancedInput"});
```

## Criando os assets

Os assets que formam o sistema de enhanced input são: [[Input Mapping Context]], [[Input Action]], Player Mappable Input Config, Force Feedback Effect, Force Feedback Attenuation. Eles estão disponíveis no menu:

![[Input.png]]