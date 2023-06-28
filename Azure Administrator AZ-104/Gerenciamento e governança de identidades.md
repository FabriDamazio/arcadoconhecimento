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