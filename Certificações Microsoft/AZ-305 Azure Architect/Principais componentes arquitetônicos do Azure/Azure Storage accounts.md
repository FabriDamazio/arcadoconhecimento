Uma conta de armazenamento fornece um namespace exclusivo para os dados do Armazenamento do Azure que podem ser acessados de qualquer lugar do mundo por HTTP ou HTTPS. Os dados nesta conta são seguros, altamente disponíveis, duráveis e maciçamente escalonáveis.

|**Tipo**|**Serviços com suporte**|**Opções de redundância**|**Usage**|
|---|---|---|---|
|Uso geral v2 Standard|Armazenamento de Blobs (incluindo Data Lake Storage), Armazenamento de Filas, Armazenamento de Tabelas e Arquivos do Azure|LRS, GRS, RA-GRS, ZRS, GZRS, RA-GZRS|Tipo de conta de armazenamento básico para blobs, compartilhamento de arquivos, filas e tabelas. Recomendado para a maioria dos cenários que usam o Armazenamento do Azure. Caso deseje obter suporte para o NFS (Network File System) nos Arquivos do Azure, use o tipo de conta de compartilhamentos de arquivos premium.|
|Blobs de blocos Premium|Armazenamento de Blobs (incluindo Data Lake Storage)|LRS, ZRS|Tipo de conta de armazenamento Premium para blobs de blocos e blobs de acréscimo. Recomendado para cenários com altas taxas de transação ou que usam objetos menores ou exigem uma latência de armazenamento sempre baixa.|
|Compartilhamentos de arquivos Premium|Arquivos do Azure|LRS, ZRS|Tipo de conta de armazenamento Premium somente para compartilhamentos de arquivos. Recomendadas para aplicações de escala empresarial ou de alto desempenho. Use esse tipo de conta caso deseje ter uma conta de armazenamento que dê suporte a compartilhamentos de arquivos SMB e NFS.|
|Blobs de página Premium|Blobs de páginas somente|LRS|Tipo de conta de armazenamento Premium somente para blobs de páginas.|

## Storage account endpoints

Cada conta de armazenamento no Azure deve ter um nome de conta exclusivo no Azure. A combinação do nome da conta e do ponto de extremidade de serviço do Armazenamento do Azure forma os pontos de extremidade da sua conta de armazenamento.

Mais informações:

- [[Azure Storage]]
- [[Azure Blob Storage]]
- [[Azure Files]]
- [[Azure Tables]]

