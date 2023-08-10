Conceitos básicos para se tornar um administrador Azure:

## Utilizar as ferramentas da Azure

- **Portal Azure**: através do portal é possível criar, gerenciar e monitorar todos recursos disponíveis na Azure.
- **Azure Cloud Shell**: shell interativo que executa no navegador. Pode ser escolhido bash ou PowerShell. Necessita de um File Share (compartilhamento de arquivo) do Azure Storage.
- **Azure PowerShell**: é um módulo adicionado ao PowerShell para gerenciar os recursos.
- **Azure CLI**: programa de linha de comando multiplataforma para gerenciar os recursos.

## Account, Tenant e Subscription

As diferenças entre elas:
- **Account/User:** é uma pessoa ou um programa. Possui um email e senha. É a base pra autenticação. Toda conta é parte de pelo menos um Tenant.
- **Tenant:** representa uma organização usualmente representada por um domínio público (por exemplo dominio.com). Nem toda tenant precisa de uma subscription.
- **Subscription:** esta dentro das tenants e é usado para cobrança e organização dos recursos.
## Conhecer o Azure Resource Manager

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

## Configurar recursos usando modelos do Azure Resource Manager

Benefícios do modelo:

- **Consistência**: linguagem comum independente de ferramenta ou SDK.
- **Exibem implantações complexas**: ajudam a visualizar recursos na ordem correta de implantação.
- **Reduzem tarefas manuais**: diminui a possibilidade de erros.
- **Modelos são código**: é um tipo de infraestrutura como código.
- **Promovem reutilização**: contém parametros que podem ser preenchidos quando executados.
- **Simplificam orquestração**: implantar o modelo para implantar todos recursos.

Os modelos são escritos em JSON como no exemplo abaixo:

````json
{
    "$schema": "http://schema.management.azure.com/schemas/2019-04-01/deploymentTemplate.json#",
    "contentVersion": "",
    "parameters": {},
    "variables": {},
    "functions": [],
    "resources": [],
    "outputs": {}
}
````

Valores a serem preenchidos na implantação podem ser definidos com um limite para 256 parâmetros:


````json
"parameters": {
    "<parameter-name>" : {
        "type" : "<type-of-parameter-value>",
        "defaultValue": "<default-value-of-parameter>",
        "allowedValues": [ "<array-of-allowed-values>" ],
        "minValue": <minimum-value-for-int>,
        "maxValue": <maximum-value-for-int>,
        "minLength": <minimum-length-for-string-or-array>,
        "maxLength": <maximum-length-for-string-or-array-parameters>,
        "metadata": {
        "description": "<description-of-the parameter>"
        }
    }
}
````

### Azure Bicep

É uma linguagem específica de domínio (DSL) que usa sintaxe declarativa para implantar recursos e pode ser usada no lugar do JSON. Ela fornce algumas melhorias em relação ao JSON como sintaxe mais simples, módulos, gerenciamente automático de dependências e IntelliSense.

### Modelos de início rápido

São modelos criados pela comunidade que podem ajudar como ponto de partida para seu modelo. O arquivo azuredeploy.json define os recursos que serão implantados e o azuredeploy.parameters.json fornece os valores de que o modelo precisa.

## Automatizar usando script com Poweshell

**PowerShell** é fornecido em duas variantes: Windows PowerShell e PowerShell 7.x, que podem ser instalados no Windows, macOS e Linux. O módulo **Az PowerShell** precisa ser instalado para adicionar os comandos da Azure.

O PowerShell permite gravar comandos e executá-los imediatamente. Isso é conhecido como **modo interativo**.

### cmdlets do PowerShell

Um comando do PowerShell é chamado de um **cmdlet** (pronunciado "comând-lét"). Um cmdlet é um comando que manipula um único recurso. O PowerShell base possui diversos cmdlets porém é possível instalar novos comandos. Os cmdlets seguem uma convenção de nomenclatura de verbo-substantivo. Por exemplo, `Get-Process`, `Format-Table` e `Start-Service`.

Os cmdlets são fornecidos em _módulos_. Um módulo do PowerShell é uma DLL que inclui o código para processar cada cmdlet disponível.

### Az PowerShell

**Az** é o nome formal do módulo do Azure PowerShell que contém cmdlets para trabalhar com os recursos do Azure.

### Scripts do PowerShell

Um script do PowerShell é um arquivo de texto que contém comandos e constructos de controle. Os comandos são invocações de cmdlets. Os constructos de controle estão programando recursos como loops, variáveis, parâmetros, comentários etc., fornecidos pelo PowerShell. Arquivos de script do PowerShell têm uma extensão de arquivo **.ps1**.

Se você está gravando scripts do PowerShell no Windows, você pode usar o ISE (Ambiente de Script Integrado).

Uma vez que você tenha escrito o script, execute-o na linha de comando do PowerShell, passando o nome do arquivo precedido por um ponto e uma barra invertida:

````Powershell
.\myScript.ps1
````

Variáveis e loops:

````Powershell
$loc = "East US"
$adminCredential = Get-Credential

For ($i = 1; $i -lt 3; $i++)
{
    $i
}
````

Passando parâmetros:

````Powershell
.\setupEnvironment.ps1 -size 5 -location "East US"
````

Capturando parâmetros no script:

````Powershell
param([string]$location, [int]$size)
````



---
Tags: #azure #az-104
