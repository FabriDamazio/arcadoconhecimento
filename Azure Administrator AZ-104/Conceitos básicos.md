Conceitos básicos para se tornar um administrador Azure:

## 1. Utilizar as ferramentas da Azure

- **Portal Azure**: através do portal é possível criar, gerenciar e monitorar todos recursos disponíveis na Azure.
- **Azure Cloud Shell**: shell interativo que executa no navegador. Pode ser escolhido bash ou PowerShell. Necessita de um File Share (compartilhamento de arquivo) do Azure Storage.
- **Azure PowerShell**: é um módulo adicionado ao PowerShell para gerenciar os recursos.
- **Azure CLI**: programa de linha de comando multiplataforma para gerenciar os recursos.

## 2. Conhecer o Azure Resource Manager

O Azure Resource Manager permite trabalhar com os recursos da sua solução como um grupo. Você pode implantar, atualizar ou excluir todos os recursos da sua solução em uma única operação coordenada. Ele fornece recursos de segurança, auditoria e marcação para gerenciar seus recursos.

É uma camada de gerenciamento consistente para realizar tarefas por meio do Azure PowerShell, CLI do Azure, portal do Azure, API REST e SDKs de cliente através de uma mesma API.

### Benefícios

- Gerenciar, implantar e monitorar recursos em grupo
- Implantar a mesma solução repetidamente de forma consistente
- Definir as dependências entre os recursos para que eles sejam implantados na ordem correta.
- Aplicar o controle de acesso a todos os serviços no grupo
- Aplicar tags nos recursos para organizar melhor os recursos
- Exibir custos por grupo de recursos

### Provedores de recursos

Um provedor de recursos é um serviço que fornece os recursos que você pode implantar e gerenciar por meio do Gerenciador de Recursos. Por exemplo, se você quiser armazenar chaves e segredos, trabalhe com o provedor de recursos **Microsoft.KeyVault**. Este provedor de recursos oferece um tipo de recurso denominado cofres para criar o cofre da chave.

O nome de um tipo de recurso está no formato: **{provedor-de-recursos}/{tipo-de-recurso}**. Por exemplo, o tipo de cofre de chaves é **Microsoft.KeyVault/vaults**.

### Grupos de recursos

Os grupos de recursos são uma coleção lógica de recursos e que segue as seguintes regras:

- Recursos só podem existir em um grupo
- Recursos não podem ser renomeados
- Um grupo de recurso pode ter recursos de tipos diferentes
- Um grupo de recurso pode ter recursos de diferentes regiões

Fatores importantes a se considerar ao definir seu grupo de recursos:

- Os recursos no grupo devem compartilhar o mesmo ciclo de vida. Você os implanta, atualiza e exclui juntos.
- Os recursos podem ser adicionados ou removidos de um grupo a qualquer momento.
- Os recursos podem ser movidos de grupo com algumas limitações.
- Um recurso pode interagir com recursos em outros grupos. Essa interação é comum quando dois recursos estão relacionados, mas não compartilham o mesmo ciclo de vida.
- Os recursos podem ter controle de acesso para somente leitura e exclusão .

Quando quiser reorganizar seus recursos movendo para outro grupo ou assinatura é importante lembrar que tanto o grupo de origem quanto o de destino ficam bloqueados para alterações durante a operação mas continuam respondendo. Antes de iniciar o processo é importante consultar a documentação pois existem algumas limitações.


