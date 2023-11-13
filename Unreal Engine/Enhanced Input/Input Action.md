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
    void AFooBar::SetupPlayerInputComponent(UInputComponent* PlayerInputComponent)
    {
        UEnhancedInputComponent* Input = Cast<UEnhancedInputComponent>(PlayerInputComponent);
        // You can bind to any of the trigger events here by changing the "ETriggerEvent" enum value
        Input->BindAction(AimingInputAction, ETriggerEvent::Triggered, this, &AFooBar::SomeCallbackFunc);
    }

    void AFooBar::SomeCallbackFunc(const FInputActionInstance& Instance)
    {
        // Get the value of the Input Action for whatever type you want here...
        FVector VectorValue = Instance.GetValue().Get<FVector>();
        FVector2D 2DAxisValue = Instance.GetValue().Get<FVector2D>();
        float FloatValue = Instance.GetValue().Get<float>(); 
        bool BoolValue = Instance.GetValue().Get<bool>();

        // Do your cool stuff here!
    } 
```

