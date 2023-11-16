A classe actor possui Delegates para notificar o inicio e o final de overlap de um component.

```cpp
// No arquivo PrimitiveComponent.h

// Início do overlap - OnComponentBeginOverlap
DECLARE_DYNAMIC_MULTICAST_SPARSE_DELEGATE_SixParams( FComponentBeginOverlapSignature, UPrimitiveComponent, OnComponentBeginOverlap, UPrimitiveComponent*, OverlappedComponent, AActor*, OtherActor, UPrimitiveComponent*, OtherComp, int32, OtherBodyIndex, bool, bFromSweep, const FHitResult &, SweepResult);

// Final do overlap - OnComponentEndOverlap
DECLARE_DYNAMIC_MULTICAST_SPARSE_DELEGATE_FourParams( FComponentEndOverlapSignature, UPrimitiveComponent, OnComponentEndOverlap, UPrimitiveComponent*, OverlappedComponent, AActor*, OtherActor, UPrimitiveComponent*, OtherComp, int32, OtherBodyIndex);
```

Podemos então adiciona um component para detectar colisões do nosso blueprint. Por exemplo, podemos adicionar um __USphereComponent__ para isso:

```cpp
// No arquivo de header
UPROPERTY(VisibleAnywhere)
TObjectPtr<USphereComponent> SphereComponent;

// No construtor
AItem::AItem()
{
// Cria o USphereComponent, define seu radius inicial e faz a ligação com o RootComponent
	SphereComponent = CreateDefaultSubobject<USphereComponent>(TEXT("Sphere"));
	SphereComponent.Get()->InitSphereRadius(85.f);
	SphereComponent.Get()->SetupAttachment(GetRootComponent());
}
```

Depois da classe construída podemos criar uma member function e fazer o Bind de  ao Delegate na função __BeginPlay__:

```cpp
// No arquivo de Header
// Função tem a mesma assinatura do delegate.
UFUNCTION()
void OnSphereOverlap(UPrimitiveComponent* OverlappedComponent, AActor* OtherActor, UPrimitiveComponent* OtherComp, int32 OtherBodyIndex, bool bFromSweep, const FHitResult& SweepResult);

UFUNCTION()
void OnSphereEndOverlap(UPrimitiveComponent* OverlappedComponent, AActor* OtherActor, UPrimitiveComponent* OtherComp, int32 OtherBodyIndex);

// Na função BeginPlay no .cpp
void AItem::BeginPlay()
{
	Super::BeginPlay();

	// Faz o bind da duas member functions aos delegates correspondentes
	SphereComponent->OnComponentBeginOverlap.AddDynamic(this, &AItem::OnSphereOverlap);
	SphereComponent->OnComponentEndOverlap.AddDynamic(this, &AItem::OnSphereEndOverlap);
}

// Implementa as member functions
void AItem::OnSphereOverlap(UPrimitiveComponent* OverlappedComponent, AActor* OtherActor, UPrimitiveComponent* OtherComp, int32 OtherBodyIndex, bool bFromSweep, const FHitResult& SweepResult)
{
	const FString OtherName = FString("Overlap with actor: ") + OtherActor->GetName();
	
	if (GEngine)
	{
		GEngine->AddOnScreenDebugMessage(1, 3.f, FColor::Red, OtherName);
	}
}

void AItem::OnSphereEndOverlap(UPrimitiveComponent* OverlappedComponent, AActor* OtherActor, UPrimitiveComponent* OtherComp, int32 OtherBodyIndex)
{
	const FString OtherName = FString("End Overlap with actor: ") + OtherActor->GetName();

	if (GEngine)
	{
		GEngine->AddOnScreenDebugMessage(1, 3.f, FColor::Blue, OtherName);
	}
	
}

```

