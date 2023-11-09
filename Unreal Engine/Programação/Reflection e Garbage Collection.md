C++ não possui reflection mas a Unreal Engine possui seu próprio sistema para isso. Ele existe para coletar dados para dados para o editor da Unreal, expor dados para os blueprints e para garbage collection.

A Unreal Header Tool é o programa responsável por coletar as informações quando o projeto é compilado. Ele gera o código quando encontra as macros especificas no código C++ e essas macros que permitem esses dados serem coletados. Uma macro também pode ou não receber parâmetros.

No exemplo abaixo temos as macros UCLASS(), GENERATED_BODY(), UPROPERTY() e UFUNCTION() por exemplo:

![[macro.png]]