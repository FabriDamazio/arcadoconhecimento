O produto escalar nos permite calcular o ângulo _θ_ (Theta) entre os vetores. Mais informações na página da Wikipedia sobre [produto escalar](https://pt.wikipedia.org/wiki/Produto_escalar).

Vetor A e vetor B e o ângulo formado entre eles:
![[Produtoescalar.png]]

A fórmula:

![[produtoescalar5.png]]

Mas com usamos sempre vetores normalizados (então eles possuem valor de 1), podemos simplificar a fórmula:

![[produtoescalar6.png]]

Entretanto, essa expressão permite o cálculo do ângulo _θ_ entre os vetores utilizando arco cosseno:
![[produtoescalar7.png]]
Então se multiplicarmos os dois lado pelo arco cosseno vemos que o arco cosseno do produto dos vetores é igual ao ângulo Theta:

![[produtoescalar8.png]]


## Caso de uso de exemplo

Queremos fazer um inimigo reagir a um ataque sofrido. Queremos ativar uma animação que desloque a posição do inimigo com base na direção do ataque:

Se for atacado pela direita, queremos que ele se desloque para a esquerda:
![[Inimigodireita.png]]
Se for atacado pela esquerda, queremos que ele se desloque para a direita:
![[Inimigoesquerda.png]]

Se olharmos nosso inimigo em uma visão top-down, podemos traçar um vetor do ponto central do inimigo até o ponto do hit do ataque. Este vetor vai formar um ângulo o forward vector do ator inimigo:

![[produtoescalar2.png]]

Para calcular esse vetor entre o ActorLocation e o Impact point usamos a fórmula para encontrar o vetor pelo seu ponto inicial e final ([[Vetores]]), que é: vetor = ponto final - ponto inicial:

![[produtoescalar3.png]]

Depois de achar o vetor usamos a formula do produto escalar (explicada no começo do documento) para calcular o ângulo Theta desses dois vetores.

O produto escalar sempre vai retornar um valor de ângulo positivo e isso que dizer que não podemos saber ainda se o vetor (verde na imagem acima) está a direita ou a esquerda do forward vector. Para saber isso devemos utilizar a formula de [[Produto vetorial (cross product)]]. 

Além disso, caso necessário, podemos deixar o vetor verde que representa o vetor de impacto paralelo ao chão (assim como o forward vector). Isso é necessário caso a rotação no eixo Z não nos interesse (ver como fazer no código C++ mais abaixo).

Com o ângulo calculado podemos então determinar de qual direção veio o ataque:
![[produtoescalar4.png]]

Um exemplo de como realizar todos os cálculos acima usando C++:
```cpp
void AEnemy::DirectionalHitReact(const FVector& ImpactPoint)
{
	// Recupera o Forward Vector do Ator
	const FVector ForwardVector = GetActorForwardVector();

	// Deixa o vetor de impacto paralelo ao chão utilizando a coordenada
	// do eixo Z do ator
	const FVector ImpactLowered = FVector(ImpactPoint.X, ImpactPoint.Y, GetActorLocation().Z);

	// Calcula o vetor dos dois pontos e normaliza
	const FVector ToHit = (ImpactLowered - GetActorLocation()).GetSafeNormal();

	// Usa o produto escalar para achar o cosseno de Theta
	// Ele sempre retorna um escalar positivo por isso mais a baixo
	// temos que calcular o produto vetorial para ver se deveria ser negativo
	const double CosTheta = FVector::DotProduct(ForwardVector, ToHit);

	// Calcula o arco cosseno do cosseno de Theta para achar o valor em radianos do
	// ângulo Theta
	double Theta = FMath::Acos(CosTheta);

	// Transforma o ângulo Theta de radianos para graus
	Theta = FMath::RadiansToDegrees(Theta);

	// Faz o produto vetorial para encontrar o valor do vetor em Z para
	// saber se o ângulo esta a direita ou a esquerda
	FVector CrossProduct = FVector::CrossProduct(ForwardVector, ToHit);

	// Se o vetor em Z estiver apontando pra baixo então o ângulo Theta deveria
	// ser negativo. Neste caso então trocamos o sinal
	if (CrossProduct.Z < 0.f)
	{
		Theta *= -1.f;
	}

	// Agora com o ângulo calculado podemos determinar qual animação vamos utilizar
	// com base em seu valor
	FName SectionName = FName("FromBack");

	if (Theta >= -45.f && Theta < 45.f)
	{
		SectionName = FName("FromFront");
	}
	else if (Theta >= -135.f && Theta < -45.f)
	{
		SectionName = FName("FromLeft");
	}
	else if (Theta >= 45.f && Theta < 135.f)
	{
		SectionName = FName("FromRight");
	}

	PlayHitReactMontage(SectionName);
}
```