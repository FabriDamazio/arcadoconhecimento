---
Criado: 2025-05-27T16:37
Atualizado: 2025-05-31T18:45
Estudado: 2025-05-31T18:45
Links:
  - "[[Sistemas de Coordenadas para Grids Hexagonais]]"
---
---
# Sistema de coordenadas Cube

O sistema de **Coordenadas Cube** é uma das abordagens para identificar hexágonos em um grid hexagonal. Ele se destaca por sua **simetria elegante** e é frequentemente considerado o sistema **mais elegante para algoritmos**. A característica fundamental deste sistema é a **restrição** de que a soma das três coordenadas deve ser sempre zero: **q + r + s = 0**. Esta propriedade permite derivar uma coordenada a partir das outras duas.

Outra maneira de enxergar grades hexagonais é perceber que existem **três eixos principais**, diferente dos dois eixos presentes em grades quadradas.

Vamos imaginar uma grade cúbica e recortar um plano diagonal onde **x + y + z = 0**:

![[Pasted image 20250528103551.png]]
![[Pasted image 20250528103635.png]]
![[Pasted image 20250528103659.png]]

Essa ideia pode parecer estranha, mas ajuda bastante nos algoritmos para grades hexagonais porque **As Coordenadas cartesianas 3D** seguem as operações vetoriais padrão: podemos somar/subtrair coordenadas, multiplicar/dividir por um escalar, etc. Podemos reutilizar essas operações nas grades hexagonais. **Coordenadas deslocadas (offset)** não suportam essas operações. Elas também contam com algoritmos já estabelecidos para cálculo de distâncias, rotação, reflexão, traçado de linhas, conversão para/de coordenadas de tela, entre outros. Podemos adaptar esses algoritmos para funcionar com grades hexagonais.

Cada **direção** na grade cúbica corresponde a uma **linha** na grade hexagonal. Ela é uma combinação de **duas direções** da grade cúbica. Por exemplo, o **norte** na grade hexagonal está entre `+s` e `-r`, então cada passo para o norte envolve somar 1 a `s` e subtrair 1 de `r`. Essa lógica é usada para calcular os hexágonos vizinhos.

![[Pasted image 20250529150059.png]]

## Relação com o Sistema Axial:

*   O sistema de **Coordenadas Axial (q, r)** é **essencialmente o mesmo** que o sistema Cube. A única diferença é que a coordenada 's' não é explicitamente armazenada no sistema Axial, sendo calculada como `s = -q - r` quando necessário.
*   Ambos os sistemas, Axial e Cube, suportam operações vetoriais e simplificam muitos algoritmos em comparação com o sistema Offset.

## Algoritmos Simplificados pelo Sistema Cube

Devido à sua estrutura e suporte a operações vetoriais, muitos algoritmos são mais fáceis ou mais elegantes de implementar usando Coordenadas Cube (ou Axial):

### Cálculo de Vizinhos

Mover-se um espaço nas coordenadas hexagonais envolve alterar uma das 3 coordenadas cúbicas em **+1** e outra em **-1** (a soma deve permanecer 0). Há 3 coordenadas possíveis para incrementar em +1, e 2 restantes que podem ser decrementadas em -1. Isso resulta em **6 mudanças possíveis**, cada uma correspondendo a uma das direções hexagonais.

![[Pasted image 20250529150455.png]]

A abordagem mais simples e rápida é **pré-calcular essas permutações** e armazená-las em uma tabela de `Hex(dq, dr, ds)`:

```csharp
var hex_direction_vectors = [
    Hex(+1, 0, -1), Hex(+1, -1, 0), Hex(0, -1, +1), 
    Hex(-1, 0, +1), Hex(-1, +1, 0), Hex(0, +1, -1), 
];

public Hex HexDirection(direction)
{
	return hex_direction_vectors[direction];
}

public Hex HexAdd(hex, vec)
{
	return Hex(hex.q + vec.q, hex.r + vec.r, hex.s + vec.s);
}
    

public Hex HexNeighbor(hex, direction)
{
	return HexAdd(hex, HexDirection(direction));
}
```

Com o sistema de coordenadas em cubo, podemos armazenar diferenças entre duas coordenadas (um “vetor”) e depois somar essa diferença a uma coordenada para obter outra. É exatamente isso que a função `HexAdd` faz.

### Cálculo de Distância

Na grade cúbica 3D, a distância de Manhattan é `abs(dx) + abs(dy) + abs(dz)`. A distância em uma grade hexagonal é **a metade disso**:

![[Pasted image 20250529150545.png]]

Um exemplo de como poderia ser implementado:
```csharp
Hex HexSubtract(Hex  a, Hex b)
{
    return Hex(a.Q - b.Q, a.R - b.R, a.S - b.S);
}


int HexDistance(Hex a, Hex b)
{
	var vec = HexSubtract(a, b);
    return (Math.Abs(vec.Q) + Math.Abs(vec.R) + Math.Abs(vec.S)) / 2;
    // ou: (abs(a.q - b.q) + abs(a.r - b.r) + abs(a.s - b.s)) / 2
}

// Uma forma equivalente de escrever isso é notar que uma 
// das três coordenadas deve ser a soma das outras duas,
// e então escolher essa como a distância. Você pode preferir
// a forma com “dividir por dois” acima ou a forma com 
// “máximo” abaixo — ambas produzem o mesmo resultado:

int HexDistance(Hex a, Hex b)
{
	var vec = HexSubtract(a, b);
	return Math.Max(Math.Abs(vec.Q), Math.Abs(vec.R), Math.Abs(vec.S));
    // ou: (int)((Math.Abs(a.Q - b.Q) + Math.Abs(a.R - b.R) + Math.Abs(a.S - b.S)) / 2)
}
 ```
 
### Cálculo de linha reta

Uma linha reta entre dois hexágonos pode não ser tão trivial:

![[Pasted image 20250529151533.png]]

Os passos para calcular esta linha reta seriam:

1. Calcular a distância entre os dois hexágonos usando o [[#Cálculo de Distância]] (neste caso N=10).
2. Traçamos pontos de forma uniforme pontos entre o início e o fim usando interpolação. Cada ponto podem ser calculados pela fórmula `A + (B - A) * 1.0/N * i` para valores de `i` começando em 0 até `N` (inclusive). Na imagem acima são os pontos azul escuro. 
3. Converter cada um desses pontos de volta usando [[#Arredondamento para o hexágono mais próximo]].

```csharp
    public static List<Hex> GetHexesInLine(Hex origin, Hex destination)
    {
	    // Criada no parte de cálculo de distancia
        var n = CalcDistance(origin, destination);
        var hexes = new List<Hex>();

        for (int i = 0; i <= n; i++)
        {
            var hex = Round(Lerp(origin, destination, 1.0f / n * i));
            hexes.Add(hex);
        }

        return hexes;
    }

    private static FloatHex Lerp(Hex a, Hex b, float t)
    {
        return new FloatHex(
              FloatLerp(a.Q, b.Q, t),
              FloatLerp(a.R, b.R, t),
              FloatLerp(a.S, b.S, t)
            );
    }

    private static float FloatLerp(float a, float b, float t)
    {
        return a + (b - a) * t;
    }

```


### Cálculo de Alcance (Range)

Dado um hexágono chamado `center` e um range `N`, como saber quais hexágonos estão a N passos de alcance?

![[Pasted image 20250529160515.png]]

Podemos resolver isso a partir da fórmula de distância entre hexágonos:  
**distância = max(|q|, |r|, |s|)**.  

Para encontrar todos os hexágonos dentro de `N` passos, queremos que:  
**max(|q|, |r|, |s|) ≤ N**.

Isso significa que precisamos que as três condições sejam verdadeiras:  
**|q| ≤ N**, **|r| ≤ N**, **|s| ≤ N**.

Removendo o valor absoluto, temos:  **-N ≤ q ≤ N**, **-N ≤ r ≤ N**, **-N ≤ s ≤ N**.

Um exemplo de implementação:

```csharp
var results = new List<Hex>();
for (int q = -N; q <= N; q++)
{
    int r1 = Math.Max(-N, -q - N);
    int r2 = Math.Min(N, -q + N);
    for (int r = r1; r <= r2; r++)
    {
        int s = -q - r;
        results.Add(HexAdd(center, new Hex(q, r, s)));
    }
}
```

### Cálculo de Intersecção de Ranges



### Rotação e Reflexão


### Desenho de Anéis e Espirais


### Arredondamento para o hexágono mais próximo

Ao traçar uma linha entre dois hexágonos ou converter um pixel na tela para um hexágono (clique do mouse por exemplo), podemos ter uma ou mais coordenadas de um hexágono representadas por ponto flutuante. Converter essa coordenada para um inteiro é chamado de arredondamento.

```csharp
Hex Round(FloatHex h)
{
	// Arredondamento
	var q = Math.Round(h.Q);
	var r = Math.Round(h.R);
	var s = Math.Round(h.S);

	// Pode ser que depois de arredontar a restrição q+r+s=0 
	// seja desrespeitada. Caso aconteça, o valor de q ou r ou s
	// (nesta ordem) é alterado para a soma voltar a ser zero.
	var qDiff = Math.Abs(q - h.Q);
	var rDiff = Math.Abs(r - h.R);
	var sDiff = Math.Abs(s - h.S);

	if (qDiff > rDiff && qDiff > sDiff)
		q = -r-s;
	else if (rDiff > sDiff)
		r = -q-s;
	else
		s = -q-r;

	return new Hex(q, r, s);
}
```

### Mapas Circulares (Wraparound)


### Pathfinding



### Histórico

O sistema de coordenadas Cube foi visto pela primeira vez pelo autor do texto em uma postagem de Charles Fu em 1994. É por vezes referido como "R3 coordinates" .

Embora outros sistemas como Offset ou Doubled possam ser mais intuitivos para armazenamento de mapas retangulares (e Doubled facilita mais algoritmos que Offset), a capacidade do sistema Cube (e Axial) de lidar com operações vetoriais e sua simetria o tornam a escolha preferencial para a maioria dos algoritmos complexos em grids hexagonais. É comum converter entre sistemas quando necessário.

---
## References


PATEL, Amit. _Hexagonal Grids_. Red Blob Games, 2015. Disponível em: [https://www.redblobgames.com/grids/hexagons/](https://www.redblobgames.com/grids/hexagons/). Acesso em: 27 maio 2025.