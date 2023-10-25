## Acesso condicional

Implementado através de policies que analisam sinais como usuário, localização, device, aplicação e risco para automatizar a decisão de autorizar o acesso a recursos (aplicações e dados). Acontece depois do primeiro fator de autenticação ter sucesso.

Uma policy de acesso condicional consiste em dois componentes: assignments e access controls.

### Assignments

Assignments (atribuições) da policy controla quem, o quê, quando e em que ponto ela será aplicada. Todas as atribuições são avaliadas com lógica AND. Se você tiver mais de uma atribuição configurada, todas as atribuições deverão ser atendidas para disparar uma política.

### Access controls

Quando a política de Acesso Condicional é aplicada, é tomada uma decisão informada sobre bloquear o acesso, conceder acesso, conceder acesso com verificação extra ou aplicar um controle de sessão para habilitar uma experiência limitada.

## Role-based access control (RBAC)

O gerenciamento de acesso usando roles é conhecido como **RBAC**.

Built-in roles são roles que já existem por padrão. As mais comuns são:

- _Global administrator_: usuários com esta função têm acesso a todos os recursos administrativos no Microsoft Entra. A pessoa que se inscreve no locatário do Microsoft Entra se torna automaticamente um administrador global.
- _User administrator_:: usuários com esta função podem criar e gerenciar todos os aspectos de usuários e grupos. Além disso, ela também inclui a capacidade de gerenciar tíquetes de suporte e monitorar a integridade do serviço.
- _Billing administrator_:: usuários com esta função podem fazer compras, gerenciar assinaturas e tíquetes de suporte e monitorar a integridade do serviço.

Também é possível criar roles personalizadas (necessita uma versão premium do Microsoft Entra ID).

Para facilitar o gerenciamento de identidades nos serviços do Microsoft 365, o Microsoft Entra adicionou algumas roles padão (buld-in) específicas do serviço, cada uma delas permite acesso administrativo a um serviço do Microsoft 365. Isso significa que as roles padrão do Microsoft Entra ID podem ser usadas para fins diferentes. Há três categorias:

- Roles específicas do Microsoft Entra: essas funções concedem permissões para gerenciar recursos somente no Microsoft Entra ID.
    
- Roles específicas do serviço: para os principais serviços do Microsoft 365.
    
- Roles cross: há algumas funções no Microsoft Entra ID que abrangem vários serviços. Por exemplo, o Microsoft Entra ID tem funções relacionadas à segurança, como o Administrador de Segurança, que concedem acesso em vários serviços de segurança em Microsoft 365. Da mesma forma, na função Administrador de Conformidade, você pode gerenciar configurações relacionadas à Conformidade no Centro de Conformidade do Microsoft 365, no Exchange e assim por diante.

### Diferença entre o RBAC do Microsoft Entra e o RBAC do Azure

- RBAC do Microsoft Entra: as funções do Microsoft Entra controlam o acesso a recursos do Microsoft Entra, como usuários, grupos e aplicativos.
- RBAC do Azure: as funções do Azure controlam o acesso a recursos do Azure como máquinas virtuais ou armazenamento usando o Gerenciamento de Recursos do Azure.