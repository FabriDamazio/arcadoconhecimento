MetaSounds é um sistema de áudio de alto desempenho que fornece aos designers de áudio controle completo sobre um gráfico de Processamento de Sinal Digital (DSP) para a geração de fontes sonoras. Oferece personalização, extensibilidade através de ferramentas de terceiro, reutilização de gráficos e uma editor de design de som.

Podemos associar um [[Sound Attenuation]] ao MetaSound para controlar como ele se comporta de acordo com a distância do ouvinte.

## Criando um MetaSound

Um MetaSound pode ser criado diretamente no Content Browser escolhendo a opção **Audio>MetaSound Sorce**. 

No editor devemos importar o som que desejamos adicionando um novo input do tipo WaveAsset e selecionar o som no seu valor default. Em caso de mais de um som também é possível criar um input do tipo array de Wave Asset.

![[inputwaveasset.png]]

Depois no editor é possivel tocar o som do iput utilizando um Wave Player e personalizado de diversas maneiras. No exemplo abaixo o volume e o pitch do som esta sendo modificado de maneira aleatória:

![[waveplayer.png]]