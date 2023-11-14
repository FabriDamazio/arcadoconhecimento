Responsável pela comunicação entre o sistema de Enhanced Input e o código do projeto.

Cada Input Action deve representar algo que o player pode fazer (como agachar ou pular). Nele é possível configurar o tipo de valor que será passado ao código quando a ação foi ativada (bool, float, Vector2D e Vector). Além disso é possível associar a um ou mais [[Input Trigger]] e [[Input Modifier]].

![[inputactions.png]]

## Trigger States

Representam o estado atual da ação:

- **Triggered:** após terminada a avaliação de todos as condições de triggers e a ação foi disparada.
    
- **Started:** foi iniciada a avaliação de todos as condições de triggers.
    

- **Ongoing:** a avaliação de todos as condições de triggers esta em andamento.
    
- **Completed:**  significa que foi terminada a avaliação de todos as condições de triggers.
    

- **Canceled:** a avaliação dos triggers foi cancelada antes de ser terminada.

## Input Listeners

Listeners podem ser usados para tomar alguma decisão baseada nos Triggers States. Para fazer isso via blueprint:

![[inputliestener_blueprint.png]]

Em C++ basta fazer o bind da ação a função:

```cpp
	// Crie a propriedade da Action no header
	UPROPERTY(EditAnywhere, BlueprintReadOnly, Category = "Input")
	TObjectPtr<UInputAction> JumpAction;

	// Declaração da função no header
	protected:		
		virtual void Jump() override;	
	
	// Faça o bind nesta função
    void AFooBar::SetupPlayerInputComponent(UInputComponent* PlayerInputComponent)
    {
        UEnhancedInputComponent* Input = Cast<UEnhancedInputComponent>(PlayerInputComponent);
        // Escolha o evento de Trigger usando o "ETriggerEvent" enum value
        Input->BindAction(JumpAction, ETriggerEvent::Triggered, this, &AFooBar::Jump);
    }
	
	// Implemente o comportamento da ação
    void AFooBar::Jump(const FInputActionInstance& Instance)
    {
        // Leia o valor do input dependendo de seu tipo
        FVector VectorValue = Instance.GetValue().Get<FVector>();
        FVector2D 2DAxisValue = Instance.GetValue().Get<FVector2D>();
        float FloatValue = Instance.GetValue().Get<float>(); 
        bool BoolValue = Instance.GetValue().Get<bool>();

        // Faça a lógica desejada aqui
    } 
```

