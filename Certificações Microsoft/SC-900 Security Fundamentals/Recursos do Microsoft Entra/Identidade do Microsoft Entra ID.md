O Microsoft Entra ID é o serviço de gerenciamento de identidades e acesso baseado em nuvem da Microsoft. As organizações usam o Microsoft Entra ID para permitir que os funcionários, convidados e outras pessoas façam logon e acessem os recursos necessários.

## Tipos de identidade

Diferentes tipos de identidades são suportadas:

### User (Usuário)

Representam pessoas como funcionários e usuários externos (clientes, consultores, fornecedores e parceiros) que são divididos pela forma em que se autenticam:

- **Membro interno:** geralmente funcionários da organização e se autenticam por meio do Entra ID da própria organização.
- **Convidado interno:** organizações que colaboram com distribuidores e fornecedores configuram contas do Microsoft Entra ID internas para esses usuários, mas as designam como convidados definindo o objeto de usuário UserType como Convidado. Como convidados, eles têm permissões reduzidas no diretório. Esse é considerado um cenário legado, pois agora é mais comum usar a colaboração B2B.
- **Convidado externo:** usuários ou convidados externos, incluindo consultores, fornecedores e parceiros, normalmente se enquadram nessa categoria. O usuário autentica usando uma conta do Microsoft Entra ID externa ou um provedor de identidade externo.
- **Membro externo:** esse cenário é comum em organizações que possuem vários tenants. Seria geralmente um funcionário que pertence ao um tenant da organização acessando outro tenant da mesma organização.

### Workload identities

É uma identidade que você atribui a um software. Isso permite que o software se autentique e acesse outros serviços e recursos. Ela pode ser de três tipos:

- **Applications and service principals:** service principal é uma identidade para um aplicativo. Para que um aplicativo delegue as funções de identidade e acesso ao Microsoft Entra ID, o aplicativo deve primeiro ser registrado no Microsoft Entra ID para habilitar sua integração.
- **Managed identities:** são o tipo de service principal gerenciados automaticamente no Microsoft Entra ID que eliminam a necessidade de os desenvolvedores gerenciarem credenciais.

### Device

É um hardware, como dispositivos móveis, notebooks, servidores, impressoras, etc. Elas podem ser configuradas de diversas maneiras, como:

 - **Registered devices:** fornece aos usuários suporte para cenários BYOD (Traga seu próprio dispositivo) ou de dispositivo móvel. Os dispositivos registrados do Microsoft Entra ID se registram no Microsoft Entra ID sem exigir uma conta organizacional para entrar no dispositivo.
- **Joined:** Um dispositivo é ingressado no Microsoft Entra ID por meio de uma conta organizacional, que é usada para entrar no dispositivo. Os dispositivos ingressados no Microsoft Entra ID geralmente pertencem à organização.
- **Hybrid joined devices:** As organizações com Active Directory local podem se beneficiar implementando dispositivos ingressados no Microsoft Entra ID híbrido. Esses dispositivos são ingressados no AD local e no Microsoft Entra ID, exigindo que a conta organizacional se conecte ao dispositivo.

## Grupos

 Se você tiver várias identidades com as mesmas necessidades de acesso, poderá criar um grupo. Use os grupos para conceder permissões de acesso a todos os membros do grupo, em vez de atribuir direitos de acesso individualmente.

Há dois tipos de grupo:

- **Segurança:** é o tipo mais comum de grupo e é usado para gerenciar o acesso de usuários e dispositivos a recursos compartilhados. Os membros de um grupo de segurança podem incluir usuários (incluindo usuários externos), dispositivos, outros grupos e entidades de serviço. A criação de grupos de segurança requer uma função de administrador do Microsoft Entra ID.
    
- **Microsoft 365:** um grupo do Microsoft 365, que também é conhecido como um grupo de distribuição, é usado para agrupar usuários de acordo com as necessidades de colaboração. Por exemplo, você pode conceder aos membros do grupo acesso a uma caixa de correio compartilhada, calendário, arquivos sites do SharePoint e muito mais. Os membros de um grupo do Microsoft 365 só podem incluir usuários, incluindo usuários fora da sua organização. Como os grupos do Microsoft 365 se destinam à colaboração, o padrão é permitir que os usuários criem grupos do Microsoft 365, para que você não precise de uma função de administrador.

Os grupos podem ser configurados para permitir que membros sejam atribuídos, selecionados manualmente ou que possam ser configurados para associação dinâmica

## Identidades híbridas

A identidade híbrida é realizada por meio de provisionamento e sincronização.

- O provisionamento entre diretórios está provisionando uma identidade entre dois sistemas de serviços de diretório diferentes. Para um ambiente híbrido, o cenário mais comum para provisionamento entre diretórios é quando um usuário que já está no Active Directory é provisionado no Microsoft Entra ID.
- Além disso, é responsável por garantir que as informações de identidade dos usuários e grupos locais correspondam às da nuvem.

Um dos métodos disponíveis para realizar o provisionamento e a sincronização entre diretórios é por meio da sincronização de nuvem do Microsoft Entra ID Connect. O agente de provisionamento de sincronização usa a especificação de Sistema de Gerenciamento de Usuários entre Domínios (SCIM) para provisionar e desprovisionar usuários e grupos. A especificação SCIM é um padrão usado para automatizar a troca de informações de identidade de usuário ou grupo entre domínios de identidade.

## Identidades externas

O recurso Identidades Externas do Microsoft Entra ID refere-se a todas as maneiras pelas quais você pode interagir com usuários fora da organização com segurança.

As seguintes funcionalidades compõem identidades externas:

- B2B collaboration

A colaboração B2B permite que os funcionários de uma organização colaborem com usuários externos. São representados em seu diretório, normalmente como usuários convidados. Não há credenciais associadas a usuários de colaboração B2B. Em vez disso, eles se autenticam com sua organização ou seu provedor de identidade e depois sua organização verifica a qualificação do usuário convidado para colaboração B2B. Essas identidades podem ser gerenciadas como as identidades do diretório (grupos, autorização, etc)

- B2B direct connect

A conexão direta B2B é uma nova maneira de colaborar com outras organizações do Microsoft Entra ID usando canais compartilhados do Microsoft Teams. Com a conexão direta B2B, você cria relações de confiança de duas vias com outras organizações do Microsoft Entra ID para permitir que os usuários se conectem diretamente aos seus recursos compartilhados e vice-versa. Usuários de conexão direta B2B não são representados no seu diretório do Microsoft Entra ID (eles não são adicionados como convidados), mas são visíveis no canal compartilhado do Teams e podem ser monitorados nos seus relatórios do centro de administração.

- Microsoft Entra External ID for customers (preview)

O Microsoft Entra External ID para clientes é a nova solução de gerenciamento de acesso e identidade do cliente (CIAM) da Microsoft. Esta solução se destina a empresas que desejam disponibilizar aplicativos para seus clientes usando a plataforma do Microsoft Entra para identidade e acesso. Os recursos incluem SSO, personalizar visual da tela de registro e login e gerenciamento de conta (perfil, exclusão , MFA, etc).

- Microsoft Entra multi-tenant organization

Uma organização multi-tenant é uma organização que possui mais de uma instância do Microsoft Entra ID. Há vários motivos para o uso da multi-tenant, por exemplo, usar várias nuvens ou ter vários limites geográficos. As organizações multi-tenant usam um serviço de sincronização unidirecional no Microsoft Entra ID, chamado sincronização entre tenants.