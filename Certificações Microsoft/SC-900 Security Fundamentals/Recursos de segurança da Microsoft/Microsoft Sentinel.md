 O Microsoft Sentinel é uma solução de SIEM/SOAR escalável e cloud native. Possibilita habilitar operações de segurança de ponta a ponta, em um SOC (Centro de Operações de Segurança) moderno.
## O que é o SIEM (gerenciamento de eventos e informações de segurança)?

Um sistema SIEM é uma ferramenta usada por uma organização para coletar dados de todo o espaço, incluindo infraestrutura, software e recursos. O sistema faz análise, procura correlações ou anomalias e gera alertas e incidentes.

## O que é o SOAR (resposta automatizada de orquestração de segurança)?

Um sistema SOAR usa alertas de várias fontes, como um sistema SIEM. Depois, o sistema SOAR dispara fluxos de trabalho e processos automatizados baseados em ação para executar tarefas de segurança que atenuam o problema.

### Conecte o Sentinel aos seus dados

Para a integração do Microsoft Sentinel, você precisa se conectar às suas fontes de segurança. Ele vem com muitos conectores para soluções da Microsoft e de outras empresas.

## Workbooks

Depois de conectar as fontes de dados ao Microsoft Sentinel, você poderá monitorar os dados usando a integração aos Workbooks do Azure Monitor. Elas são destinadas a engenheiros e analistas do SOC para visualização, análise de dados e criação de relatórios.

## Analytics

O Microsoft Sentinel usa analytics para correlacionar alertas a incidentes. Incidentes são grupos de alertas relacionados que, juntos, criam uma possível ameaça acionável que você pode investigar e resolver.

## Gerenciar incidentes no Microsoft Sentinel

O gerenciamento de incidentes permite que você gerencie o ciclo de vida do incidente. Visualize todos os alertas relacionados que são agregados em um incidente. Você também pode fazer triagem, investigar, alterar o status ou atribuir incidentes a indivíduos para investigação.

## Security automation and orchestration with playbooks

O Microsoft Sentinel integra-se ao Azure Logic Apps para que você crie workflows automatizados ou playbooks em resposta a eventos.

## Notebooks

Você pode usar Jupyter notebooks no Microsoft Sentinel para estender o escopo do que você pode fazer com os dados. Por exemplo, execute análises que não são estão disponíveis no Sentinel, como alguns recursos de machine learning do Python, crie visualizações de dados como linhas do tempo e árvores de processo personalizadas, ou integre fontes de dados fora como um conjunto de dados local.

