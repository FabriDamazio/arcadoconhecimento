É um repositório de objetos extremamente escalonável para objetos de dados.
Ele oferece um sistema de arquivos, um repositório de mensagens e um repositório NoSQL.

Podemos considerar compatível com três categorias de dados: dados estruturados (banco de dados), dados não estruturados (blobs, etc) e dados de máquina virtual (discos).

## Serviços fornecidos

Os quatro serviços de dados oferecidos:

- **Azure blob Storage (containers):** otimizados para dados não estruturados ou não relacionais (imagens ou documentos diretos no navegador, streaming de áudio e vídeo, backups, etc). O endpoint padrão é: **`mystorageaccount`**`.blob.core.windows.net`
- **Azure Files (Arquivos do Azure):** compartilhamento de arquivos de rede altamente disponível usando protocolo SMD e NFS. Usado principalmente em máquinas virtuais. O endpoint padrão é: **`mystorageaccount`**`.file.core.windows.net`
- **Azure Queue Storage (Filas):** usado para guardar e recuperar mensagens. Uma fila pode conter milhões de mensagens para serem processadas de forma assíncrona. O endpoint padrão é: **`mystorageaccount`**`.queue.core.windows.net`
- **Azure Table Storage (Azure Cosmos DB):** banco de dados NoSQL totalmente gerenciado. O endpoint padrão é: **`mystorageaccount`**`.table.core.windows.net`

Os domínios de qualquer serviço pode ser personalizado.

## Estratégias de replicação


- **Locally redundant storage (LRS):** a opção de menor custo. Indicado para dados não essenciais.
- **Zone redundant storage (ZRS):** replicação para 3 clusters de armazenamento separados fisicamente em uma mesma região.
- **Geo-redundant storage (GRS):** replicação para uma região secundária. Possui dois modos: apenas leitura possível caso um failover da Microsoft seja iniciado (GRS). Leitura mesmo sem failover (RA-GRS). 
- **Geo-zone-redundant storage (GZRS):** replicação para 3 clusters de armazenamento separados fisicamente em uma mesma região e  replicação para uma região secundária.

## Segurança de endpoints do storage

O acesso ao serviço pode ser restrito a sub-redes específicas em redes virtuais ou IP públicos (sub-redes devem existir na mesma região ou par do serviço).

