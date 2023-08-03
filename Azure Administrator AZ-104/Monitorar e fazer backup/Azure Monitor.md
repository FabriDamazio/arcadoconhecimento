Solução para coletar, analisar e responder a dados de telemetria cloud e on premise.

Os dados de métricas e logs que são armazenados podem ter diversas fontes, inclusive API REST e são armazenados por 90 dias.

## Alertas

Um alerta consiste em _regras de alertas (alert rules)_ que combinam as configurações e as condições que você deseja monitorar. Esta regra especifica um  _grupo de ações (action groups)_ que realizaram uma ou mais etapas quando o alerta é disparado.

Há três estados de alertas:
- **Novo**: o problema é novo (em aberto) e não está em análise.
- **Reconhecido**: o problema está em análise, e o trabalho está em andamento.
- **Fechado**: o problema foi concluído.

## Log Analytics

É uma ferramenta do Azure Monitor para editar e executar consultas de log para os dados coletados. O Log Analytics dá suporte à KQL (Kusto Query Language) para consultas dos logs.

Para começar a usar o Log Analytics no Azure Monitor, você precisa criar seu workspace. Cada workspace tem uma ID de workspace e uma ID de recurso exclusivas. Depois de criar seu workspace, você configura suas fontes de dados e soluções para armazenar os dados em seu workspace.