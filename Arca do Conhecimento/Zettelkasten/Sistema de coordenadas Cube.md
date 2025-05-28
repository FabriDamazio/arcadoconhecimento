---
Criado: 2025-05-27T16:37
Atualizado: 2025-05-27T16:37
Estudado: 2025-05-27T16:37
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

![[Pasted image 20250528104427.png]]

## Relação com o Sistema Axial:

*   O sistema de **Coordenadas Axial (q, r)** é **essencialmente o mesmo** que o sistema Cube. A única diferença é que a coordenada 's' não é explicitamente armazenada no sistema Axial, sendo calculada como `s = -q - r` quando necessário.
*   Ambos os sistemas, Axial e Cube, suportam operações vetoriais e simplificam muitos algoritmos em comparação com o sistema Offset.

## Algoritmos Simplificados pelo Sistema Cube

Devido à sua estrutura e suporte a operações vetoriais, muitos algoritmos são mais fáceis ou mais elegantes de implementar usando Coordenadas Cube (ou Axial):

### Cálculo de Vizinhos

Mover-se um espaço nas coordenadas hexagonais envolve alterar uma das 3 coordenadas cúbicas em **+1** e outra em **-1** (a soma deve permanecer 0). Há 3 coordenadas possíveis para incrementar em +1, e 2 restantes que podem ser decrementadas em -1. Isso resulta em **6 mudanças possíveis**, cada uma correspondendo a uma das direções hexagonais.

![[Pasted image 20250528112124.png]]

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

![[Pasted image 20250528114351.png]]

```csharp
public Hex HexSubtract(a, b)
{
    return Hex(a.q - b.q, a.r - b.r, a.s - b.s);
}


public int HexDistance(a, b)
{
	var vec = HexSubtract(a, b);
    return (abs(vec.q) + abs(vec.r) + abs(vec.s)) / 2;
    // ou: (abs(a.q - b.q) + abs(a.r - b.r) + abs(a.s - b.s)) / 2
}

// Uma forma equivalente de escrever isso é notar que uma 
// das três coordenadas deve ser a soma das outras duas,
// e então escolher essa como a distância. Você pode preferir
// a forma com “dividir por dois” acima ou a forma com 
// “máximo” abaixo — ambas produzem o mesmo resultado:

public int HexDistance(a, b)
{
	var vec = HexSubtract(a, b);
	return max(abs(vec.q), abs(vec.r), abs(vec.s))
    // ou: max(abs(a.q - b.q), abs(a.r - b.r), abs(a.s - b.s))
}
 ```
 
### Cálculo de Alcance (Range)


### Rotação e Reflexão


### Desenho de Anéis e Espirais


### Arredondamento


### Mapas Circulares (Wraparound)


### Pathfinding



### Histórico

O sistema de coordenadas Cube foi visto pela primeira vez pelo autor do texto em uma postagem de Charles Fu em 1994. É por vezes referido como "R3 coordinates" .

Embora outros sistemas como Offset ou Doubled possam ser mais intuitivos para armazenamento de mapas retangulares (e Doubled facilita mais algoritmos que Offset), a capacidade do sistema Cube (e Axial) de lidar com operações vetoriais e sua simetria o tornam a escolha preferencial para a maioria dos algoritmos complexos em grids hexagonais. É comum converter entre sistemas quando necessário.

---
## References


PATEL, Amit. _Hexagonal Grids_. Red Blob Games, 2015. Disponível em: [https://www.redblobgames.com/grids/hexagons/](https://www.redblobgames.com/grids/hexagons/). Acesso em: 27 maio 2025.