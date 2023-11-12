Podemos expor as funções (functions) criadas em uma classe C++ para que possam ser usadas dentro da Unreal Engine. A macro UFUNCTION deve ser colocada acima da propriedade e podemos passar os diversos parâmetros para definir seu comportamento:

- **BlueprintCallable:** para criar funções que alteram o estado (cor azul). Elas possuem o execution pin;
- **BlueprintPure:** para  criar funções puras, que apenas fazem um cálculo (cor verde). Não possuem execution pin.

