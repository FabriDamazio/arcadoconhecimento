## Azure Active Directory (Azure AD)

Serviço multi-tenant de gerenciamento de diretório e identidade. Pode ser usado para para dar suporte a acesso a recursos internos (rede corporativa) e externos.

### Principais conceitos

- **Identidade (identity):** é um objeto que pode ser autenticado. Pode ser um usuário, aplicação ou outros servidores.
- **Conta (account):** é a identidade que tem dados associados a ela. Para ter uma conta deve-se primeiro ter uma identidade válida.
- **Conta Azure AD (Azure AD account):** é uma identidade criada através do Azure AD ou outro serviço cloud Microsoft como o 365.
- **Azure Tenant (directory):** Tenant (locatário) é uma única instância dedicada do Azure AD. Cada tenant (diretório) representa uma única organização.
- **Azure Subscription (subscrição ou assinatura):** uma subscription é usada para pagar por serviços da Azure. Cada assinatura é associada a uma única tenant.

### Active Directory Domain (AD DS) vs Azure Active Directory

AD DS é um serviço de active directory tradicional de Windows. Ele não é um solução de identidade completa como o Azure AD. O Azure AD não utiliza autenticação Kerberos, implementa protocolos HTTP/HTTPS como SAML, WS-Federation e OpenID Connect para autenticação e OAuth para autorização.


### Implementar ingresso (join) no Azure AD

O Azure AD permite SSO para dispositivos, aplicativos e serviços. Alguns dos benefícios:

- **SSO (logon único):** para serviços e aplicativos SAAS gerenciados pela Azure.
- **Enterprise Roaming State:** sincronizar configurações do usuário ou aplicativo ingressado.
- **Microsoft Store para Empresas, Windows Hello e restrições de acesso**


### Redefinição de senha self-service 

O recurso do SSPR (self-service password reset) do Azure AD permite os usuários a redefinir a própria senha. 

Requer uma conta do Azure AD com privilégios de **Administrator Global**, A SSPR utiliza um grupo de segurança para limitar os usuários e todas contas de usuários da organização devem ter uma licença validar para utiliza-lo.

### Contas de usuários

Existem 3 tipos:

- **Identidade de nuvem (Cloud Identity):** uma conta de usuária definida apenas no Azure AD
- **Identidade sincronizada com diretório:** São definidas em um Active Directory on premise e sincronizado com o Azure AD através do Azure AD Connect.
- **Usuário convidado (guest user):** definidos fora da Azure como por exemplo outros provedores de nuvem. Útil caso é necessário acesso de fora aos seus recursos da Azure.

#### Gerenciando contas de usuário

Contas de usuário podem ser criadas pelo portal da Azure, Centro de Administração do Microsoft 365, console de administração do Microsoft Intune ou do Azure CLI.

A conta possui um nome de exibição um nome de conta (só pode ser modificado por administradores). Já outros dados podem ser modificados pelo próprios usuários se necessário.

Os usuários podem ser criados em massa através de arquivos CSV pelo portal da Azure ou o PowerShell.

#### Contas de grupo

Existem dois tipos: 
- **grupos de segurança:** para gerenciar acesso a a recursos. Podem apenas ser definidos por administradores.
- **grupos do Microsoft 365:** oferecem oportunidades de colaboração em recursos compartilhados como caixa de email, calendário, etc. Podem ser definidos por usuários normais.

Ao adicionar membros em grupos, existem 3 maneiras de atribuir direitos de acesso (access rights):

- **Atribuído (assigned):** adicione usuários específicos como membro do grupo.
- **Usuário dinâmico (Dynamic user):** adiciona e remove dinamicamente do grupo quando os atributos do usuário atendem os requisitos do grupo.
- **Dispositivo dinâmico (Dynamic device):** somente para grupos de segurança.  Adiciona e remove dinamicamente dispositivos do grupo quando os atributos do dispositivo atendem os requisitos do grupo.

#### Unidades administrativas

Usadas para ter uma autoridade central para para gerenciar organizações que possuem muitas divisões independentes.

