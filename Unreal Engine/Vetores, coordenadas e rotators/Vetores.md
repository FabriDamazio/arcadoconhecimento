Para representar uma grandeza, podemos usar apenas números. É o caso da massa e do comprimento de uma mesa, por exemplo. Basta afirmar que sua massa é de 100kg e seu comprimento, de 1m. No entanto, nem sempre um número é suficiente: às vezes, é preciso saber a orientação de uma grandeza.

É o caso do deslocamento, que pode ser expresso por meio de uma flecha. Isso porque não basta saber quantos metros uma pessoa andou, mas a direção e o sentido em que ela se deslocou.

Essa é uma aplicação de vetores, uma representação matemática que sempre apresentará três propriedades: magnitude (também chamado de módulo, norma ou intensidade), direção e sentido.

- A **direção** do **vetor** é a reta onde o **vetor** atua. podemos classificar essa **direção** como sendo horizontal, vertical diagonal e ainda podemos dar a **direção** pelo ângulo em relação a um eixo de referência. 

- O **sentido** do **vetor** é dado pela ponta da flecha. O **sentido** indica para que lado o **vetor** atua.

- A **magnitude** corresponde, do ponto de vista geométrico, ao seu comprimento.

## Coordenadas do vetor

As coordenadas podem ser calculadas subtraindo os pares ordenados do ponto onde ele começa (origem do vetor) e um outro ponto onde ele termina (extremidade do vetor).

Por exemplo:
![[vetor1.png]]

Fórmula:
![[vetor3.png]]

Vetores que tem exatamente a mesma direção e mesma magnitudes são considerados iguais. Por exemplo:

![[vetor2.png]]


## Operações com vetores

### Multiplicação por uma grandeza escalar

Multiplicar uma vetor por um escalar é simples. Basta multiplicar suas coordenadas pelo escalar:

![[vetor_multiplicacao.png]]

## Divisão por uma grandeza escalar

Para dividir por um escalar, as coordenadas do vetor devem ser divididas pelo escalar (ou multiplicada por 1/2):

![[vetor_divisao.png]]

## Adição de vetores

Para somar dois vetores deve-se somar o valor de suas coordenadas correspondentes:

![[vetor_adicao.png]]
![[vetor_adicao2.png]]
## Subtração de vetores

Para somar dois vetores deve-se subtrair o valor de suas coordenadas correspondentes:

![[vetor_substracao.png]]![[vetor_substracao2.png]]

## Calculando a magnitude de um vetor

Para calcular a magnitude de um vetor (seu comprimento) devemos utilizar o teorema de Pitágoras:

![[vetor_magnitude.png]]

Por exemplo, se tivermos um player (representado em azul) e o inimigo (representado em vermelho), podemos usar o teorema de Pitágoras para calcular a distancia entre eles (representado em verde). Primeiro calculamos as coordenadas do vetor verde e depois aplicamos o teorema para encontrar sua magnitude:

![[vetor_magnitude2.png]]

## Normalização de vetores

Em um jogo temos diferentes atores se movendo pelo mundo em diferentes velocidades. Imagine um player sendo atacado por dois inimigos:

![[vetor_unit.png]]

Para calcular seu deslocamento temos que traçar um vetor em direção ao player e com a magnitude relativa a sua velocidade e move-los em direção ao player:

![[vetor_unit2.png]]

Este tipo de cálculo pode ficar facilmente complicado quando temos dezenas de coisas se movento pela tela. Para simplificar o cálculo usamos VETORES UNITÁRIOS (unit vectors).

### VETORES UNITÁRIOS (unit vectors)

Vetores unitários são **vetores cuja magnitude é equivalente a exatamente 1 unidade**. 

Isso que dizer que no exemplo acima podemos "normalizar" os vetores dos dois inimigos fazendo com que cada um dos vetores tenha apenas 1 unidade e depois multiplicar pela sua velocidade.

Para normalizar um vetor podemos multiplicar seu valor por 1/seu valor e assim encontramos o vetor unitário correspondente:

![[vetor_unit3.png]]