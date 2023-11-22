A Animation Montage proporciona uma maneira de controlar as animações diretamente de Blueprints ou C++. Nela podemos combinar diferentes sequências de animação em um único asset e acessa-las de forma individual ou combinada. Além disso é possível disparar notificações (notifies) que permitem executar tarefas em reação a ela como por exemplo tocar um som ou diminuir a contagem de munição de uma arma.

Exemplo de uma Animation Montage com diferentes animações separadas em **Montage Sections** e disparando diferentes Notifies:
![[LoopingMontageDemo.gif]]

## Exemplo em C++

```cpp
// No seu header do Character crie a propriedade do Montage
UPROPERTY(EditDefaultsOnly, Category = "Montage")
TObjectPtr<UAnimMontage> AttackMontage;
```

Depois ele deve ser atribuído no Blueprint:
![[Pasted image 20231121213323.png]]

```cpp
// 
void AMainCharacter::PlayAttackMontage()
{
	UAnimInstance* AnimInstance = GetMesh()->GetAnimInstance();
	if (AnimInstance && AttackMontage)
	{
		AnimInstance->Montage_Play(AttackMontage);
		const int32 Selection = FMath::RandRange(0, 2);
		switch (Selection)
		{
		case 0:
			AnimInstance->Montage_JumpToSection(FName("Attack1"), AttackMontage);
			break;
		case 1:
			AnimInstance->Montage_JumpToSection(FName("Attack2"), AttackMontage);
			break;
		case 2:
			AnimInstance->Montage_JumpToSection(FName("Attack3"), AttackMontage);
			break;
		default:
			AnimInstance->Montage_JumpToSection(FName("Attack1"), AttackMontage);
			break;
		}
	}
}
```