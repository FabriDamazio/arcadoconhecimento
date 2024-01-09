
## Azure Storage

Mais informações em [[Azure Storage]]

O Azure Storage oferece diversas opções de armazenamento:

|Conta de armazenamento|Serviços com suporte|Uso recomendado|
|---|---|---|
|[**Standard** **general-purpose v2**](https://learn.microsoft.com/en-us/azure/storage/common/storage-account-upgrade) |Armazenamento de Blobs (incluindo Data Lake Storage), Armazenamento de Filas, Armazenamento de Tabelas e Arquivos do Azure|Conta de armazenamento padrão para a maioria dos cenários, incluindo blobs, compartilhamentos de arquivos, filas, tabelas e discos (blobs de página).|
|[**Premium** **block blobs**](https://learn.microsoft.com/en-us/azure/storage/blobs/storage-blob-block-blob-premium/) |Armazenamento de Blobs (incluindo Data Lake Storage)|Conta de armazenamento Premium para blobs de blocos e blobs de acréscimo. Recomendado para aplicativos com altas taxas de transação. Use blobs de blocos Premium se você trabalha com objetos menores ou precisa de latência de armazenamento consistentemente baixa. Esse armazenamento foi criado para dimensionar com seus aplicativos.|
|[**Premium** **file shares**](https://learn.microsoft.com/en-us/azure/storage/files/storage-how-to-create-file-share) |Arquivos do Azure|Conta de armazenamento Premium somente para compartilhamentos de arquivos. Recomendadas para aplicações de escala empresarial ou de alto desempenho. Use compartilhamentos de arquivos Premium se você precisa de suporte para compartilhamentos de arquivos SMB e NFS.|
|[**Premium** **page blobs**](https://learn.microsoft.com/en-us/azure/storage/blobs/storage-blob-pageblob-overview) |Blobs de páginas somente|Conta de armazenamento de alto desempenho Premium somente para blobs de páginas. Os blobs de páginas são ideais para armazenar estruturas de dados esparsas e baseadas em índice, como sistemas operacionais, discos de dados para máquinas virtuais e bancos de dados.|

### Redundância na região primária

Oferece duas opções para a replicação dos dados na região primária: **locally redundant storage and zone-redundant storage.**

![[Pasted image 20240109080314.png]]

### Redundância em uma região secundária

Oferece duas opções para a replicação dos dados na região secundária: **geo-redundant storage** and **geo-zone-redundant storage**.

![[Pasted image 20240109080413.png]]

## Azure Files

Mais informações em[[Azure Files]].

## Azure Managed Disks

Os discos de dados são usados por máquinas virtuais para armazenar dados como arquivos de banco de dados, conteúdos estáticos de sites ou códigos de aplicativo personalizados. O número de discos de dados que pode ser adicionado depende do tamanho da máquina virtual. Cada disco de dados tem uma capacidade máxima de 32.767 GB.

|Comparação|Disco Ultra|SSD Premium|SSD Standard|HDD Standard|
|---|---|---|---|---|
|**Tipo de disco**|SSD|SSD|SSD|HDD|
|**Cenário**|Cargas de trabalho com uso intensivo de E/S (como o SAP HANA), bancos de dados de camada superior (como o SQL e o Oracle) e outras cargas de trabalho com muitas transações|Cargas de trabalho sensíveis à produção e ao desempenho|Servidores Web, aplicativos empresariais pouco usados, desenvolvimento e teste|Backup, não crítico, acesso não frequente|
|**Taxa de transferência máxima**|2.000 Mbps|900 Mbps|750 Mbps|500 Mbps|
|**IOPS Máxima**|160.000|20.000|6.000|2.000|