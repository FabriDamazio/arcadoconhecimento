## Azure Backup

Oferece vários componentes que você pode baixar e implantar no local apropriado, como no computador, no servidor ou na nuvem. O componente (ou agente) que você implanta depende daquilo que deseja proteger:

|Tipo de backup|Descrição|
|---|---|
|**Local**|Faça backup de arquivos, pastas e do estado do sistema com o agente do MARS (Serviços de Recuperação do Microsoft Azure). Você também pode usar o DPM (Data Protection Manager) do System Center ou o agente do MABS (Servidor de Backup do Microsoft Azure) para proteger as máquinas virtuais locais (do Hyper-V e do VMware) e outras cargas de trabalho locais.|
|**Máquinas Virtuais do Azure**|Faça backup das máquinas virtuais do Windows/Linux inteiras (usando extensões de backup) ou faça backup de arquivos, de pastas ou do estado do sistema com o agente de MARS.|
|**Arquivos do Azure**|Faça backup do Azure files share em uma conta de armazenamento. |
|**SQL Server em máquinas virtuais do Azure**|Faça backup de bancos de dados do SQL Server em execução nas máquinas virtuais do Azure.|
|**Bancos de dados SAP HANA em máquinas virtuais do Azure**|Faça backup do bancos de dados do SAP HANA em execução nas máquinas virtuais do Azure.|
|**Nuvem da Microsoft**|O Backup do Azure pode substituir sua solução de backup local ou externa existente por uma solução baseada em nuvem que é confiável, segura e de custo competitivo.|
###  Storage vaults

- **Azure Backup vault**:  são usados apenas com o Azure Backup. As fontes de dados com suporte incluem os servidores do Banco de Dados do Azure para PostgreSQL, blobs do Azure e discos do Azure.
    
- **Azure Recovery Services vault**: podem ser usados com o Azure Backup ou o Azure Site Recovery. As fontes de dados com suporte incluem máquinas virtuais do Azure, SQL ou SAP HANA em uma máquina virtual do Azure e compartilhamentos de arquivos do Azure.


## Azure blob backup and recovery

Uma solução de backup local para Armazenamento de Blobs do Azure. Nesse método de backup, seus dados de backup são armazenados na conta de armazenamento do Azure na origem.

- O backup operacional para blobs do Azure fornece uma solução _de backup contínuo_. Você não precisa agendar nenhum backup.
- O período de retenção para blobs ou contêineres excluídos pode ser especificado entre 1 e 365 dias. O período padrão é de sete dias.

## Azure files backup and recovery

 Fornecem a capacidade de fazer snapshots do file share.

## Azure virtual machine backup and recovery

Usado para fazer backups de instantâneo e restaurar os dados nas máquinas virtuais se houver corrupção de dados ou exclusão acidental.

## Azure SQL backup and recovery

Os backups de banco de dados permitem a restauração do banco de dados para um ponto no tempo especificado e dentro de um período de retenção configurado.

O Banco de Dados SQL e a Instância Gerenciada de SQL utilizam a tecnologia SQL Server para criar backups completos toda semana, backups diferenciais a cada 12-24 horas e backups de log de transações a cada 5 a 10 minutos. A frequência dos backups de logs de transações é baseada no tamanho da computação e na quantidade de atividade do banco de dados.

## Azure Site Recovery

Fornece recursos de BCDR para seus aplicativos no Azure, no local e em outros provedores de nuvem. O serviço oferece planos para ajudar a automatizar sua recuperação de desastre. Você pode definir como as máquinas virtuais fazem failover e a ordem em que elas são reiniciadas após o failover bem-sucedido.

