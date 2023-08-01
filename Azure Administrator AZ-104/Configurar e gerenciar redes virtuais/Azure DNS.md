Permite hospedar os domínios DNS.

## Nome de domínio inicial e personalizado

Quando sua assinatura Azure é criada, um Azure AD da conta é criado e um nome de domínio inicial é aplicado a ela. O nome de domínio inicial tem o formato **seu_dominio.onmicrosoft.com**. Ele não pode ser alterado ou excluído mas pode ser adicionado um nome personalizado (que precisa ser um endereço verificado).

## Zona DNS

Uma **zona DNS** do Azure hospeda os registros DNS de um domínio. O nome de uma zona DNS precisa ser exclusivo em um grupo de recursos.

## Zona de DNS privada

Você ganha resolução de nomes de máquinas virtuais em uma rede virtual e entre redes virtuais.

## Segurança

Possui controle de acesso role-based, logs de atividades e bloqueio de recursos.

## Domínio apex

O domínio apex é o nível mais alto do seu domínio. O domínio apex às vezes também é chamado de _apex da zona_ ou _apex raiz_. Geralmente são representados pelo símbolo @ nos registros da zona DNS.

# Registros de alias (alias records)

Os registros de alias do Azure habilitam um domínio apex de zona a fazer referência a outros recursos do Azure da zona DNS.

Ele pode apontar para os seguintes recursos do Azure:

- Um perfil do Gerenciador de Tráfego
- Azure Content Delivery Network endpoints
- Um recurso de IP público
- Um perfil de front door

Vantagens de seu uso:

- **Impede que os registros DNS fiquem pendentes**
- **Atualiza o conjunto de registros DNS automaticamente quando os endereços IP são alterados**
- **Hospeda aplicativos com balanceamento de carga no apex da zona**
- **Aponta o apex de zona para Azure Content Delivery Network endpoints**

