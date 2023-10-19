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

### Grupos

 Se você tiver várias identidades com as mesmas necessidades de acesso, poderá criar um grupo. Use os grupos para conceder permissões de acesso a todos os membros do grupo, em vez de atribuir direitos de acesso individualmente.

Há dois tipos de grupo:

- **Segurança:** é o tipo mais comum de grupo e é usado para gerenciar o acesso de usuários e dispositivos a recursos compartilhados. Os membros de um grupo de segurança podem incluir usuários (incluindo usuários externos), dispositivos, outros grupos e entidades de serviço. A criação de grupos de segurança requer uma função de administrador do Microsoft Entra ID.
    
- **Microsoft 365:** um grupo do Microsoft 365, que também é conhecido como um grupo de distribuição, é usado para agrupar usuários de acordo com as necessidades de colaboração. Por exemplo, você pode conceder aos membros do grupo acesso a uma caixa de correio compartilhada, calendário, arquivos sites do SharePoint e muito mais. Os membros de um grupo do Microsoft 365 só podem incluir usuários, incluindo usuários fora da sua organização. Como os grupos do Microsoft 365 se destinam à colaboração, o padrão é permitir que os usuários criem grupos do Microsoft 365, para que você não precise de uma função de administrador.

Os grupos podem ser configurados para permitir que membros sejam atribuídos, selecionados manualmente ou que possam ser configurados para associação dinâmica