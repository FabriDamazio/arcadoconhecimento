Oferece armazenamento compartilhado para aplicações usando o protocolo padrão SMB. 
Ideal para migrar aplicativos por lift and shift quando já usam APIs nativas do sistema de arquivos. Também uma boa opção para armazenar ferramentas de desenvolvimento e debugging que precisam ser acessadas de diversas máquinas virtuais.

## Configuração

Pontos importantes:

- **Abrir a porta 445:** o protocolo SMB usa esta porta. A porta deve ser aberta e também liberada no firewall do computador cliente.
- **Transferência segura:** Habilite a opção *Secure Transfer required* para habilitar apenas conexões REST HTTPS.
- **Mapear para Windows e Linux:** é possível mapear o compartilhamento em computadores Windows e Linux.
- **Snapshots (instantâneos):** são incrementais porém podem só o último precisa ser mantido.  Protege contra dados corrompidos, exclusões acidentais e da suporte para backup e recuperação.

## Azure File Sync

Permite armazenar em cache vários compartilhamentos do Azure Files em um Windows Server local ou máquina virtual na nuvem. Com isos você pode centralizar o compartilhamento de arquivos sem abrir mão da flexibilidade, desempenho e compatibilidade de um servidor local.

Componentes da Sincronização de Arquivos do Azure:
- **Storage Sync Service:** serviço de auto nível de sincronização.
- **Sync group:** define a topologia de sincronização para um conjunto de arquivos.
- **Registered server:**  representa uma relação de confiança entre o servidor (ou o cluster) e o recurso de sincronização.
- **Azure File Sync agent:**  pacote que permite que o Windows Server seja sincronizado.
- **Server endpoint:** representa um local específico em um servidor registrado, como uma pasta em um volume do servidor.
- **Cloud endpoint:** é um compartilhamento do Azure Files que faz parte de um sync group.

