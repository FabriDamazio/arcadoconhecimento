O sistema de Groom (sistema de enfeites em tradução livre) oi projetado para lidar com fios de cabelo de arquivos importados no formato Groom Alembic(.abc). No entanto, para fins de escalabilidade, também suporta representações geométricas alternativas usando cards e meshes.

O Groom Asset Editor gerencia a maioria dos aspectos do seu Groom asset, permitindo que você modifique várias partes do asset quanto à forma como ele é renderizado, como ele lida com a simulação física, criando e gerenciando níveis de detalhe (LODs) e muito mais.


## Adicionando ao ser Character

O módulo _HairStrandsCore_ precisa ser adicionado ao seu projeto no C++:

```cpp
PublicDependencyModuleNames.AddRange(new string[] { "Core", "CoreUObject", "Engine", "InputCore", "EnhancedInput", "HairStrandsCore", "Niagara" });
```

Assim o _UGroomComponent_ poderá ser adicionado ao sua classe:

```cpp
// No header criando a propriedade
UPROPERTY(VisibleAnywhere, Category = "Hair")
TObjectPtr<UGroomComponent> Hair;

UPROPERTY(VisibleAnywhere, Category = "Hair")
TObjectPtr<UGroomComponent> EyeBrows;

// Criando e atribuindo no construtor
AMainCharacter::AMainCharacter()
{ 	
	Hair = CreateDefaultSubobject<UGroomComponent>(TEXT("Hair"));
	Hair.Get()->SetupAttachment(GetMesh());
	Hair.Get()->AttachmentName = FString("head");

	EyeBrows = CreateDefaultSubobject<UGroomComponent>(TEXT("EyeBrows"));
	EyeBrows.Get()->SetupAttachment(GetMesh());
	EyeBrows.Get()->AttachmentName = FString("head");
}
```

Depois basta atribuir no BP de seu Character:

![[addgroom.png]]