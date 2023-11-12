Podemos expor as variáveis criadas em uma classe C++ para que possam ser modificadas dentro da Unreal Engine no painel de detalhes (Details). A macro UPROPERTY deve ser colocada acima da propriedade e podemos passar os diversos parâmetros para definir seu comportamento:

## Para expor a variável do painel de detalhes (details)

- **EditAnywhere:** a variável poderá ser editada nos detalhes Blueprint default e na instância.
- **EditInstanceOnly:** editável somente nos detalhes da instância.
- **EditDefaultsOnly:** editável apenas nos detalhes do Blueprint default.
- **VisibleDefaultsOnly:** a variável fica visível nos detalhes do Blueprint default porém não é editável.
- **VisibleInstanceOnly:** fica visível nos detalhes da instância e o valor pode ser visto em runtime porém não é editável.
- **VisibleAnywhere:** fica visível nos detalhes da instância, do Blueprint default e o valor pode ser visto em runtime porém não é editável.

## Para expor no Event Graph para edição em runtime

Não pode ser do tipo private.

- **BluePrintReadOnly:** expõe no event graph apenas para leitura (GET).
- **BluePrintReadWrite:** expõe no event graph para leitura e escrita (GET e SET).

Caso seja realmente necessário expor uma propriedade privada para o event graph pode se usar:

- meta = (AllowPrivateAcess = "true")

## Para expor a variável dentro de uma categoria

 - **Category = "nome da categoria":** Podemos passar  o parametro **Category** e o nome da categoria para que ela seja exposta dentro de uma categoria especificada.


Um exemplo de como passar os parâmetros:

![[expor_variaveis.png]]

