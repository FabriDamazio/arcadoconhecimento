Solução para coletar, analisar e responder a dados de telemetria cloud e on premise.

Os dados de **métricas e logs** que são armazenados podem ter diversas fontes, inclusive API REST e são armazenados por 90 dias.

É sistema automático que começa a coletar dados dessas fontes assim que você cria recursos. Você pode estender os dados coletados de duas maneiras:

- **Habilitando o diagnóstico**: para alguns recursos, como o Banco de Dados SQL do Azure, você só receberá informações completas sobre um recurso depois de habilitar o log de diagnósticos nele.
- **Adicionando um agente**: para máquinas virtuais, você pode instalar o agente do Log Analytics e configurá-lo para enviar dados para um workspace do Log Analytics. Esse agente aumenta a quantidade de informações enviadas ao Azure Monitor.

## Alertas

Um alerta consiste em _regras de alertas (alert rules)_ que combinam as configurações e as condições que você deseja monitorar. Esta regra especifica um  _grupo de ações (action groups)_ que realizaram uma ou mais etapas quando o alerta é disparado.

Há três estados de alertas:
- **Novo**: o problema é novo (em aberto) e não está em análise.
- **Reconhecido**: o problema está em análise, e o trabalho está em andamento.
- **Fechado**: o problema foi concluído.

Severidades:
- **0**: Critical
- **1**: Error
- **2**: Warning
- **3**: Informational
- **4**: Verbose

Pode executar as seguintes ações:

- Enviar um email
- Enviar uma mensagem SMS
- Criar uma notificação por push do aplicativo do Azure
- Fazer uma chamada de voz para um número
- Chamar uma função do Azure
- Disparar um aplicativo lógico
- Enviar uma notificação para um webhook
- Criar um ticket do ITSM
- Usar um runbook (para reiniciar uma VM ou escalar ou reduzir uma VM verticalmente)

## Log Analytics

É uma ferramenta do Azure Monitor para editar e executar consultas de log para os dados coletados. O Log Analytics dá suporte à KQL (Kusto Query Language) para consultas dos logs.

Para começar a usar o Log Analytics no Azure Monitor, você precisa criar seu workspace. Cada workspace tem uma ID de workspace e uma ID de recurso exclusivas. Depois de criar seu workspace, você configura suas fontes de dados e soluções para armazenar os dados em seu workspace.