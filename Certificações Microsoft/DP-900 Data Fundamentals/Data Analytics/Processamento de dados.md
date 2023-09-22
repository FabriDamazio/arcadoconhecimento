O processamento de dados é a conversão de dados brutos em informações relevantes por meio de um processo.

## Processamento em lotes (batch)

Os dados são coletados e armazenados e o grupo inteiro é processado juntos como um lote. O momento exato em que cada grupo é processado é definido de acordo com a conveniência.

Vantagens: pode ser agendado para quando for conveniente (por exemplo quando os computadores estão ociosos fora do horário de pico).

Desvantagens: intervalo entre a coleta e o processamento, todos os dados devem estar pronto para ser processados e qualquer problema durante o processo pode levar a uma parada.

## Processamento de fluxo (stream)

Cada parte dos dados é processada ao chegar. Não há espera até o próximo intervalo como no processamento de lotes. Essa abordagem é benéfica nos cenários em que dados dinâmicos são gerados de maneira contínua como por exemplo telemetria, logs, sistema de tempos reais, iot, etc.