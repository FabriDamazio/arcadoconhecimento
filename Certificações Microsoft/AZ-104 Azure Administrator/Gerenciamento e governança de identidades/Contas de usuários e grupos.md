## Contas de usuários

Existem 3 tipos:

- **Identidade de nuvem (Cloud Identity):** uma conta de usuária definida apenas no Azure AD
- **Identidade sincronizada com diretório:** São definidas em um Active Directory on premise e sincronizado com o Azure AD através do Azure AD Connect.
- **Usuário convidado (guest user):** definidos fora da Azure como por exemplo outros provedores de nuvem. Útil caso é necessário acesso de fora aos seus recursos da Azure.

### Gerenciando contas de usuário

Contas de usuário podem ser criadas pelo portal da Azure, Centro de Administração do Microsoft 365, console de administração do Microsoft Intune ou do Azure CLI.

A conta possui um nome de exibição um nome de conta (só pode ser modificado por administradores). Já outros dados podem ser modificados pelo próprios usuários se necessário.

Os usuários podem ser criados em massa através de arquivos CSV pelo portal da Azure ou o PowerShell.

## Contas de grupo

Existem dois tipos: 
- **grupos de segurança:** para gerenciar acesso a a recursos. Podem apenas ser definidos por administradores.
- **grupos do Microsoft 365:** oferecem oportunidades de colaboração em recursos compartilhados como caixa de email, calendário, etc. Podem ser definidos por usuários normais.

Ao adicionar membros em grupos, existem 3 maneiras de atribuir direitos de acesso (access rights):

- **Atribuído (assigned):** adicione usuários específicos como membro do grupo.
- **Usuário dinâmico (Dynamic user):** adiciona e remove dinamicamente do grupo quando os atributos do usuário atendem os requisitos do grupo.
- **Dispositivo dinâmico (Dynamic device):** somente para grupos de segurança.  Adiciona e remove dinamicamente dispositivos do grupo quando os atributos do dispositivo atendem os requisitos do grupo.

### Unidades administrativas

Usadas para ter uma autoridade central para para gerenciar organizações que possuem muitas divisões independentes.