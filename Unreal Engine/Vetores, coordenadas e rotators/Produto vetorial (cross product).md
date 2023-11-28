Dados dois vetores independentes linearmente **a** e **b**, o produto vetorial **a** × **b** é um vetor perpendicular ao vetor **a** e ao vetor **b** e é a normal do plano contendo os dois vetores. Seu resultado difere do [[Produto escalar (Dot Product)]] por ser também um vetor, ao invés de um escalar.

É importante, por exemplo, para determinar se vetor esta a direita ou a esquerda depois de um cálculo de [[Produto escalar (Dot Product)]].

![[produtovetorial.png]]

## Calculando o produto vetorial em C++

```cpp
	// Dado um ângulo Theta qualquer obtido através do cálculo de produto escalar...
	
	// Faz o produto vetorial para encontrar o valor do vetor em Z para
	// saber se o ângulo esta a direita ou a esquerda
	FVector CrossProduct = FVector::CrossProduct(ForwardVector, ToHit);

	// Se o vetor em Z estiver apontando pra baixo então o ângulo Theta deveria
	// ser negativo. Neste caso então trocamos o sinal
	if (CrossProduct.Z < 0.f)
	{
		Theta *= -1.f;
	}
```