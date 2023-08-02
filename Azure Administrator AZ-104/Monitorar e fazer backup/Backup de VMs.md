Existem várias opções para fazer backup de VMs na Azure:

### Azure Backup

Tira snapshots da VMs e armazena em recovery vaults.

- Os snapshots, por padrão, são retidos por dois dias (pode ser de 1 a 5).
- Os snapshots incrementais são armazenados como zure page blobs (Azure Disks).
- Quando o snapshot é tirado, é identificado como *snapshot*.
- Quando o snapshot é transferido pro vault, é identificado como *snapshot and vault*.
- Para discos standard o tamanho é até 23TB. Para premium limite de até 10TB
## Azure Site Recovery

Protege a VMs de interrupções completas em uma região. Replica as VMs e workloads para um local secundário.
## Azure managed disks - snapshot

Snapshot gerenciado pelo próprio disco gerenciado.
## Azure managed disks - image

Cria uma imagem armazenada em um Azure Storage.

## System Center Data Protection Manager (DPM) e Microsoft Azure Backup Server (MABS)

Usados para fazer backup de cargas de trabalho especializadas como Sharepoint, Exchange, SQL Server. Na Azure eles precisam rodar em uma VM. 

DPM: Snapshots "app-aware" e requer uma assinatura ativa da Azure. Suporta arquivos, pastas, VMs, aplicações e cargas e trabalho. Salva em vault ou discos locais anexados.

MABS: Não requer server de backup separado, backups 3x por dia e suporta apenas arquivos e pastas.