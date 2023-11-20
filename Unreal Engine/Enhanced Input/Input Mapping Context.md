Representam um certo contexto em que o player pode estar. Por exemplo, os controles podem ser diferentes no menu de pausa e durante o jogo. Neste caso podemos ter um contexto diferente para cada. 

Os contextos possuem uma lista de Input Actions que são associadas a um ou mais meios de input (teclado, toque, joystick). Também podem ser associados a um ou mais [[Input Modifier]] e/ou [[Input Trigger ]]a cada uma das [[Input Action]].

![[inputmappingcontext.png]]

## Adicionando contexto ao player via Blueprint

![[imc_blueprint.png]]

## Adicionando contexto ao player via C++

```cpp
    // Criando a propriedade no header
    UPROPERTY(EditAnywhere, Category="Input")
    TSoftObjectPtr<UInputMappingContext> InputMapping;

     
    // Adicionando o contexto no beginplay
    if (ULocalPlayer* LocalPlayer = Cast<ULocalPlayer>(Player))
    {
        if (UEnhancedInputLocalPlayerSubsystem* InputSystem = LocalPlayer->GetSubsystem<UEnhancedInputLocalPlayerSubsystem>())
        {
            if (!InputMapping.IsNull())
            {
                InputSystem->AddMappingContext(InputMapping.LoadSynchronous(), Priority);
            }
        }
    }
```

