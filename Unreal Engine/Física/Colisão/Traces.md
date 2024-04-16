Os traces oferecem um método para obter feedback sobre o que está presente ao longo de um segmento de linha. Dois pontos (início e fim) devem fornecidos e o sistema físico "traça" um segmento de linha entre esses pontos, relatando quaisquer atores (com colisão) que ele atingir.

## Trace by Channel e Object type

Como o Traces usa o sistema físico, você poderá definir a categoria do item que deseja rastrear. Existem duas categorias gerais para escolher: Channels e Object types. Os channels são usados ​​para coisas como visibilidade e câmera. Object types são os tipos físicos de atores com colisão em sua cena, como veículos, atores destrutíveis e assim por diante.

Tipos personalizados podem ser adicionados ao projeto.

## Single or Multiple Hits

Podemos optar por retornar a primeira coisa que corresponda aos critérios atingidos pelo trace ou  retornar tudo o que for atingido pelo trace que corresponda aos critérios.

## Hit Result

Quando um Trace atinge algo, ele retorna uma estrutura Hit Result que esta disponível nos Blueprints e em C++. Essa struct possui informações do ponto de impacto, ator atingido, entre outros.



