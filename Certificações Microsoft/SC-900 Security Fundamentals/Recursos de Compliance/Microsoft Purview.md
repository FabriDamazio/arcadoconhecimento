O portal de conformidade do Microsoft Purview reúne todas as ferramentas e os dados necessários para ajudar a entender e gerenciar as necessidades de conformidade de uma organização.

Está disponível para clientes com SKU Microsoft 365 com uma das seguintes roles:

- Global administrator
- Compliance administrator
- Compliance data administrator

A home page do portal de conformidade padrão contém vários cards, incluindo:

- **Compliance Manager:** mostra um score baseado em risco de compliance.
- **Solution catalog:** links para coleções de soluções integradas de compliance.
- **Active alerts:** resumo dos alertas ativos.

## Compliance Manager

É um recurso do portal de conformidade do Microsoft Purview que ajuda os administradores a gerenciar os requisitos de conformidade de uma organização, possuindo:

- Avaliações predefinidas com base em normas e padrões comuns do setor e regionais.
- Ações de aperfeiçoamento passo a passo que os administradores podem executar para ajudar a atender às normas e aos padrões relevantes para a organização.
- Calculo de score baseado em risco de compliance.

## Compliance Score

Mede o progresso ao concluir as ações de aperfeiçoamento recomendadas nos controles. A pontuação ajuda uma organização a entender sua postura atual de conformidade.

## Data Lifecycle Management

Microsoft Purview Data Lifecycle Management  gerencia o ciclo de vida de seu conteúdo usando soluções para importar, armazenar e classificar dados comercialmente críticos para que você possa manter o que precisa e excluir o restante.

O Microsoft Purview oferece três maneiras de identificar itens para que eles possam ser classificados:

- manualmente por usuários
- reconhecimento automatizado de padrões, como tipos de informações confidenciais
- aprendizado de máquina

### Content Explorer

Está disponível como uma guia no painel de data classification do portal de compliance. Ele permite que os administradores possam ver o conteúdo que foi resumido no painel de visão geral.

O acesso ao Content Explorer é altamente restrito porque torna possível ler o conteúdo dos arquivos digitalizados. Há duas funções que concedem acesso:

- Content explorer list viewer.
- Content explorer content viewer.

### Activity Explorer

Indica qual conteúdo foi descoberto e rotulado (tag), além de onde ele se encontra. Ele possibilita monitorar o que tem sido feito com o conteúdo rotulado em toda a organização. Os administradores conseguem ver as atividades de nível de documento, como alterações de rótulo e downgrades de rótulo (como quando alguém passa uma classificação do rótulo de confidencial para pública).

### Sensitivity labels

Com os rótulos de confidencialidade, as organizações podem decidir quais rótulos (tags) serão aplicados ao conteúdo, como emails e documentos, muito semelhante a como os diferentes carimbos são aplicados aos documentos físicos:

Os rótulos são:

- **Customizable:** porem ser criadas diferentes categorias.
- **Clear text:** são texto puro para que outras aplicações possam consumi-los.
- **Persistent:** uma vez aplicados, viram metadata e acompanham o documento/email.

Podem ser configurados para:

- Encriptar
- Marcar o conteúdo com marcas d'agua, cabeçalho ou rodapé.
- Rotular automaticamente.
- Proteger conteúdo com controle de acesso
- Permite que apps teceiros leiam os rótulos e possam aplicar controles.


## Data loss prevention

No Microsoft Purview, você implementa a prevenção contra perda de dados definindo e aplicando políticas DLP. Com uma política DLP, você pode **identificar, monitorar e proteger automaticamente** itens confidenciais em:

- Serviços do Microsoft 365, como contas do Teams, Exchange, SharePoint e OneDrive
- Aplicativos do Office, como Word, Excel e PowerPoint
- Pontos de extremidade do Windows 10, Windows 11 e macOS (três versões mais recentes)
- Aplicativos na nuvem
- compartilhamentos de arquivos locais e SharePoint local
- Power BI

## Retention policies and retention labels

As políticas e os rótulos de retenção ajudam as organizações a gerenciar e administrar as informações ao garantir que o conteúdo seja mantido apenas por um tempo necessário e, em seguida, excluído permanentemente. 

As configurações de retenção funcionam com:

- SharePoint e OneDrive
- Microsoft Teams
- Viva Engage
- Exchange

## Describe records management

Ajuda uma organização a cuidar de suas obrigações legais. Ele também ajuda a demonstrar a conformidade com regulamentos e aumenta a eficiência com a disposição regular de itens que não precisam mais ser mantidos, que não têm mais valor ou que não são mais necessários para fins comerciais.

Quando o conteúdo é rotulado como um registro, acontece o seguinte:

- Restrições são colocadas em vigor para bloquear determinadas atividades.
- Atividades são registradas em log.
- A prova de disposição é mantida no final do período de retenção.

