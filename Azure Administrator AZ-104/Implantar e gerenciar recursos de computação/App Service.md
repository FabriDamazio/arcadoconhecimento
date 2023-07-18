O Serviço de Aplicativo fornece guias de início rápido para vários produtos para ajudar você a criar e implantar facilmente seus aplicativos Windows e Linux.

Ao ser criado é necessário ser associado a um App Service Plan e escolhido o sistema operacional.

## Integração e implantação contínua (CI/CD)

Possui integração com Azure DevOps, Github, BitBucket, FTP ou repositório Git local. Já para implantação manual pode ser usado Git, CLI, Visual Studio ou FTP/S.

### Slots de implantação

Disponíveis a partir da versão Standard, o slot de implantação pode ser usado para se ter os seguintes benefícios: 
- **Validação:** é possível validar a nova versão no slot de implantação antes de muda-lo para produção.
- **Tempo de indisponibilidade:** evita indisponibilidade durante o deploy.
- **Rollback:** ao ser promovido para produção, a versão que estava em produção fica no slot de implantação o que permite o rollback caso necessário.

## Autenticação e Autorização

O Serviço de Aplicativo do Azure fornece suporte interno para a autenticação e autorização. Ele é executado no mesmo ambiente do aplicativo porem isolado. Ele pode ser ativado e configurado nas configurações do aplicativo e quando ligado todas solicitações HTTP passarão pelo modulo antes de ir para o aplicativo.

## Domínios personalizados

Em uma camada paga do Azure App Service é possível configurar um domínio personalizado.

## Backup e Restauração

Os backups podem ser manuais ou agendados. Esta disponível a partir da camada Standard e é necessário um contêiner e uma conta de armazenamento na mesma subscription. Podem ser salvos configurações do aplicativo, conteúdo de arquivos e banco de dados em um total combinado de 10Gb de tamanho.

## Monitoramento com Application Insights

O Azure Application Insights é um recurso do Azure Monitor que permite que você monitore seus aplicativos em funcionamento. Você pode integrar o Application Insights às suas configurações do Serviço de Aplicativo para detectar automaticamente anomalias de desempenho em seus aplicativos.

## Azure App Service plans

Em um App Service, a aplicação roda em um Plano de Serviço (plan). Ele define um conjunto de recursos de computação para um aplicativo ser executado. Você pode adicionar novos aplicativos enquanto tenha recursos suficientes. **Cada plano tem três configurações: região, numero de VMs e tamanho delas.**

Se o plano estiver configurado para executar cinco instâncias de máquinas virtuais, todos os aplicativos do plano serão executados em todas as cinco instâncias.