
A governança fornece mecanismos e processos para manter controle sobre aplicativos e recursos no Azure. A governança envolve a determinação das necessidades, o planejamento das iniciativas e a definição de prioridades estratégicas.

O primeiro passo para governança na Azure é a criação de uma hierarquia para a estrutura organizacional:

![[azurehierarquia.png]]

## Management Groups

Os grupos de gerenciamento são contêineres que ajudam você a gerenciar o acesso, a política e a conformidade de **várias assinaturas**. Você pode usar grupos de gerenciamento para:

- Limitar as regiões em que as máquinas virtuais podem ser criadas nas assinaturas. 
- Forneça acesso de usuário a múltiplas subscriptions criando uma role que seja herdada por outras assinaturas.
- Monitore e audite as atribuições de roles e policies nas subscriptions.

Alguns pontos importantes:

- a Hierarquia de management groups pode ter seis níveis de profundidade.
- RBAC não esta ativada por padrão.
- Por padrão todas novas assinaturas são colocadas abaixo da raiz do grupo.

## Subscriptions (assinaturas)

São contêineres lógicos que servem como unidades de gerenciamento, escala e limites de cobrança.

- Fornecem ambientes de cobrança distintos, como por exemplo desenvolvimento, teste e produção. 
- As políticas para cada assinatura podem ajudar a atender a diferentes padrões de conformidade.
- Você pode organizar cargas de trabalho especializadas para escalar além dos limites de uma assinatura existente. 
- Usando assinaturas, você pode gerenciar e acompanhar os custos de sua estrutura organizacional.

## Resource groups (grupos de recursos)

Os grupos de recursos são contêineres lógicos nos quais os recursos do Azure são implantados e gerenciados. Use para:

- Adicionar recursos de uso, tipo ou localização semelhantes em grupos lógicos.
- Organizar os recursos por ciclo de vida para que todos os recursos possam ser criados ou excluídos ao mesmo tempo.
- Aplicar permissões a um grupo de recursos ou conceder a um grupo acesso para administrar um grupo de recursos.
- Usar bloqueios de recursos para proteger recursos individuais contra exclusão ou alteração.

Características de grupos de recursos:

- Os grupos de recursos têm o região própria atribuída. Essa região é onde os metadados são armazenados.
- Se a região do grupo de recursos está temporariamente indisponível, você não pode atualizar os recursos no grupo de recursos porque os metadados não estão disponíveis. Os recursos em outras regiões ainda funcionam conforme o esperado, mas não é possível atualizá-los.
- Os recursos no grupo de recursos podem estar em regiões diferentes.
- Um recurso pode interagir com os recursos de outros grupos de recursos. Você pode ter um aplicativo Web que se conecta a um banco de dados em outro grupo de recursos.
- Os recursos podem ser movidos entre grupos de recursos com algumas exceções.  
- Os grupos de recursos não podem ser aninhados.
- Cada recurso deve estar somente em um grupo de recursos.
- Os grupos de recursos não podem ser renomeados.

## Tags

São outra maneira de organizar os recursos. As marcas fornecem informações extras ou metadados sobre os recursos.

- Uma tag é composta por um par nome e valor. Por exemplo, `env = production` ou `env = dev, test`.    
- Você pode atribuir uma tag a cada recurso, grupo de recursos ou assinatura do Azure.
- As tags podem ser adicionadas, modificadas e excluídas. Essas ações podem ser feitas com o PowerShell, a CLI do Azure, os modelos do ARM (Azure Resource Manager), a API REST ou o portal do Azure.
- As tags podem ser aplicadas a um grupo de recursos. No entanto, as tags aplicadas a um grupo de recursos não são herdadas pelos recursos do grupo.

## Azure Policy

É um serviço do Azure que permite criar, atribuir e gerenciar políticas que controlam ou auditam os recursos. Essas políticas impõem diferentes regras sobre as configurações dos recursos, de modo que essas configurações permaneçam em conformidade com os padrões corporativos.

- O Azure Policy permite definir políticas individuais e grupos de políticas relacionadas, conhecidas como _initiatives. 
- As políticas do Azure são herdadas na hierarquia.   
- Você pode definir o escopo e aplicar políticas do Azure em diferentes níveis na hierarquia organizacional.
- O Azure Policy avalia todos os recursos no Azure e recursos habilitados para Arc (tipos de recursos específicos que são hospedados fora do Azure).
- O Azure Policy põe em destaque os recursos que não estão em conformidade com as políticas atuais.

## Role-based access control (RBAC)

Permite acesso aos recursos do Azure que você controla. O RBAC do Azure avalia cada solicitação de acesso e determina se o acesso deve ser bloqueado, não permitido ou permitido.

## Landing Zones

Fornece um ambiente de infraestrutura para hospedar suas cargas de trabalho. As zonas de destino garantem que os princípios fundamentais sejam colocados em prática antes de implantar os serviços. São definidas por grupos de gerenciamento e assinaturas projetadas para escalar de acordo com as necessidades e prioridades de negócios.