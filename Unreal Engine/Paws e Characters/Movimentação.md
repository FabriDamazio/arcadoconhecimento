Algumas dicas para implementação de movimentação de [[Pawn]] e [[Character]]

## 1. Bind e implementação de Inputs de controle

Para movimenta-los é necessário receber inputs do Controller. Para isso é preciso criar os blueprints necessários de [[Enhanced Input]] e realizar o Bind da [[Input Action]] (contém as informações de como fazer).

Abaixo um exemplo de implementação de movimentação vertical usado em Characters humanóides (movimentação verticalmente orientado):

```cpp
void AMainCharacter::Move(const FInputActionValue& value)
{	
	const FVector2D MovementVector = value.Get<FVector2D>();

	if (Controller)
	{
		// Encontra o forward e o right vector do controller
		// Busca o Controller
		const FRotator Rotation = Controller->GetControlRotation();
		
		// Como é um humanoide que se move apenas de um lado para o outro
		// e não de cima para baixo, apenas Yaw é importante.
		// Declara um FRotator com o valor de Yaw do Controller
		const FRotator YawRotation(0.f, Rotation.Yaw, 0.f);

		// Utiliza formula de matriz de rotação para encontrar o Forward vector (eixo X)
		const FVector ForwardDirection = FRotationMatrix(YawRotation).GetUnitAxis(EAxis::X);
		// Add o movimento usando o forward vector e o valor do input no eixo Y
		// Movimento para frente e para trás
		AddMovementInput(ForwardDirection, MovementVector.Y);

		// Utiliza formula de matriz de rotação para encontrar o Right vector (eixo Y)
		const FVector RightDirection = FRotationMatrix(YawRotation).GetUnitAxis(EAxis::Y);
		// Add o movimento usando o right vector e o valor do input no eixo X
		// Movimento de um lado para o outro
		AddMovementInput(RightDirection, MovementVector.X);
	}
}
```

Um exemplo de implementação de rotação do Controller:

```cpp
void AMainCharacter::Look(const FInputActionValue& value)
{
	const FVector2D LookAxisVector = value.Get<FVector2D>();

	AddControllerPitchInput(LookAxisVector.Y);
	AddControllerYawInput(LookAxisVector.X);
}
```
## 2. Associe os Inputs e Contexto de controle ao seu blueprint

É necessário associar ao seu blueprint de Character aos blueprints de [[Input Action]] e [[Input Mapping Context]] .

![[movimentacao1.png]]


## 3. Não se deve usar a rotação do Controller

No blueprint:

![[movimentacaobp1.png]]

Ou em C++:

```cpp
// No Construtor da classe
AMainCharacter::AMainCharacter()
{ 		
	bUseControllerRotationPitch = false;
	bUseControllerRotationYaw = false;
	bUseControllerRotationRoll = false;
}
```

## 4. Configurar o SpringArm (CameraBoom)

Para a câmera rotacionar junto do Pawn deve-se utilizar sua rotação no SpringArm da câmera

No Blueprint:
![[movimentacaobp2.png]]

ou em C++:

```cpp
// No construtor da classe
AMainCharacter::AMainCharacter()
{ 	
	CameraBoom = CreateDefaultSubobject<USpringArmComponent>(TEXT("SpringArm"));
	CameraBoom.Get()->SetupAttachment(GetRootComponent());		
	CameraBoom.Get()->bUsePawnControlRotation = true;
}
```

# 5. Configurar o Character Movement Component

Rotaciona o Character na direção da aceleração.

No Blueprint:
![[movimentacaobp3.png]]

ou em C++:

```cpp
// No construtor da classe
AMainCharacter::AMainCharacter()
{ 	
	GetCharacterMovement()->bOrientRotationToMovement = true;
	// Se quiser alterar a taxa de rotação
	GetCharacterMovement()->RotationRate = FRotator(0.f, 360.f, 0.f);
}
```
