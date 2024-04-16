TSubclassOf é uma template class que fornece type safety para a  UClass. 

Por exemplo, vamos imaginar que você está criando uma classe de projétil que permite especificar o tipo de dano no Blueprint. Você poderia criar um UPROPERTY do tipo UClass e sempre atribuir uma classe derivada de UDamageType. Caso, por erro, escolha uma classe que não é derivada de UDemageType o jogo pode crashar. Para evitar isso, _TSubclassOf  de UDemageType_  pode ser usado e só  será possível escolher classes que são derivadas dele. O código de exemplo abaixo ilustra a diferença:

```cpp
	 /** Qualquer classe poderá ser escolhida. Sujeito a erro. */
	UPROPERTY(EditDefaultsOnly, Category=Damage)
    UClass* DamageType;

	 /** Apenas classes derivadas de UDamageType poderão ser escolhidas */
    UPROPERTY(EditDefaultsOnly, Category=Damage)
    TSubclassOf<UDamageType> DamageType;

```

