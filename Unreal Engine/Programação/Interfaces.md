Interface classes são usadas para garantir que diferentes classes implemente uma ou mais funcionalidades em comum.

Imagine que cada objeto que possa ser atingido pela espada do jogador deve reagir de uma maneira: se for um inimigo deve ter a vida diminuída, se for uma caixa ela deve ser quebrada e assim por diante. Uma interface pode ser criada com uma função "GetHit" e todas as classes que precisam reagir ao hit podem implementar essa interface e ter sua própria lógica da função GetHit.

## Declaração de interface

Declaração de interface class é similar a de uma classe normal com duas principais diferenças: utilizamos a macro **UINTERFACE** e herdamos de **UInterface**.

```cpp
    #pragma once

    #include "ReactToTriggerInterface.generated.h"

    UINTERFACE(MinimalAPI, Blueprintable)
    class UReactToTriggerInterface : public UInterface
    {
        GENERATED_BODY()
    };

    class IReactToTriggerInterface
    {
        GENERATED_BODY()

    public:
        /** Adicione as funções aqui */
        virtual void GetHit();
    };
```

A classe **UINTERFACE** não é a interface e sim apenas uma classe vazia para que fique visível ao sistema de reflection da Unreal Engine. Já na segunda classe é onde devemos declarar as funções.

## Interface Specifiers

Os seguintes specifiers podem ser usados na macro **UINTERFACE**:

- BlueprintType: expõe a classe como tipo para ser usado como variável nos blueprints.
- DependsOn=(ClassName1, ClassName2, ...): as classes listadas são compiladas antes dessa classe. Importante quando o classe usa uma struct ou enum declarado em outra classe.
- MinimalAPI: faz que apenas a informação de tipo da classe seja exportada para ser usada em outros módulos. Quer dizer que a classe pode ser usada para cast mas suas funções não poderão ser chamadas. Usada para melhorar o tempo de compilação.

