Dado os eixos de rotação:

![[eixosrotacao 1.png]]

Quando seu objeto estiver rotacionado em um ou mais eixos, como encontrar o [[Forward e Right Vectors]]?

Para isso utilizamos uma fórmula matemática chamada **Matriz de rotação**. 

Um exemplo: se rotacionarmos o objeto no eixo Y (Pitch) em 45 graus, os eixos X e Z mudaram de posição.

![[eixosrotacao2.png]]


Para calcular o vetor de direção de cada um deles utilizamos na Unreal Engine a classe _FRotationMatrix_, onde passamos um _FRotator_ com os ângulos de rotação em seu construtor e usar o método _GetUnitAxis_ para pegar os vetores unitários como no exemplo abaixo:

```cpp
	// Cria um Rotator para testar
	const FRotator Foo(45.f, 0.f 0.f);

	// Utiliza formula de matriz de rotação para encontrar o Forward vector (eixo X)
	const FVector ForwardDirection = FRotationMatrix(Foo).GetUnitAxis(EAxis::X);
```