Para adicionar novos módulos como dependência do seu projeto, você deve adicionar ao seu arquivo .Build do codigo a dependência do módulo:

```cpp
PublicDependencyModuleNames.AddRange(new string[] { "Core", "CoreUObject", "Engine", "InputCore", "EnhancedInput"});
```

Depois de adicionar um novo módulo deve seguir os seguintes passos:

- Feche o Visual Studio e a Unreal Engine.
- Delete as pastas Binaries, Saved e Intermediate do seu projeto.
- Clique com o botão direto no seu arquivo do projeto (.uproject) e selecione a opção "Generate Visual Studio project files".
- Abra o arquivo .uproject e seleciona YES para recompilar.
- Feche o editor e abra o arquivo .sln do projeto e compile novamente pelo Visual Studio.