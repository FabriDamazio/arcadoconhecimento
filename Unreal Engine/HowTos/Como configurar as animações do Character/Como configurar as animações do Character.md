---

excalidraw-plugin: parsed
tags: [excalidraw]

---
==⚠  Switch to EXCALIDRAW VIEW in the MORE OPTIONS menu of this document. ⚠==


# Text Elements
Como configurar as animações do Character ^XAAXgNSX

Pré-requisitos necessários ^x1pwMpRQ

O skeletal Mesh e rigs do personagem já devem
ter sido importados para o projeto. Além disso o 
Blueprint do Character já deve ter sido criado e
ter a mesh configurada.

Mais informações sobre podem ser encontradas
no How to:  ^ghHn8MKv

1 ^5SkPckVt

[[Como criar um Character]] ^8RMfLITa

Criar classe que herda de UAnimInstance ^tWqoaXCV

Criar um classe que herda de UAnimInstance para
utilizarmos como pai do nosso Animation blueprint.
Isso nos possibilita guardarmos variáveis relacionadas
as animações e criarmos outras personalizações 
em C++. Nela já fazemos override nas duas principais
members functions herdadas que é a que executa na
inicialização da animção e a outra a cada tick de 
update. ^MYGjA3JU

2 ^F828TvMs

Configurar as variáveis já existentes ^ervMy29b

Caso já existam variáveis possíveis elas já podem ser
criadas na classe C++ para que sejam herdadas pelo
blueprint. Outra prática aconselhável é controlar os 
estados das animações nesta classe com enums criados 
em uma classe header específica. ^1QsX4lkt

3 ^iK33tpYT

Criar Animation Blueprint para gerenciar os states ^TqBIuinO

Para manter o AnimGraph do nosso blueprint organizado
podemos criar opcionalmente mais um Animation blueprint
e salvar apenas as states machines nela. Podemos criar
quantos foram necessárias. Depois basta linkar todos
Animation Blueprint no Blueprint principal. ^R2V2ZOHa

5 ^E0OWnp23

Criar Animation Blueprint herdando da classe criada ^7G9h5KHx

Criar BP herdando da classe criada,
criar e configurar as state machines
necessárias no AnimGraph. Para 
facilitar a organização elas podem 
ser salvas em cache e encadeadas 
para serem conecta na pose de 
output. ^N2WUOrxW

4 ^prNmWgCp

Atribuir o Animation Blueprint ao Character ^97WV76UN

Com o Animation Blueprint pronto basta agora atribuir o blueprint
ao Character para ele usar as animações configuradas. ^0mDKK3te

6 ^sIbBfYxs

Criar blueprint de Control Rig caso preciso ^H7dtWtLJ

Se houverem personalizações que deseja fazer nas animações como
por exemplo alinhar os pés em superfícies irregulares os Control
Rigs podem ser usados. Você deve cria-los e importar o rig da 
skeletal mesh do personagem e criar solvers para fazer os cálculos.
Para que o control rig seja considerado na animação ele deve ser
referenciado no Animation Blueprint e aplicado depois das poses de
animação. ^VjmNsIyb

7 ^u4KfXBfn

Criar Animation Montages caso seja preciso ^myP4g2t2

Caso precise de um controle mais preciso de animações como 
variações da mesma animação, encadear duas ou mais animações
emitir diversos notifies dessas animações encadeadas as Animation
Montages ncessárias devem ser criadas.

 ^6ilIAJUf

8 ^1hGCGaPw

Guardar o CharacterMovementComponent
nos permite a ter acesso a dados 
importantes do movimento como a velocidade ^8RZMON3P

Enum para gerenciar estados
ajuda a criar a lógica que vai
disparar as animações ^xu1Yhm4L

Salvando em cache ^OcE0bwha

Usando o cache ^ghj4JLNF

emitindo um notify
para tocar um som ^fudLGOhL

emitindo um notify
de fimd a animação
para ser utilizado
no character ^tHrF5NMR

três animações
na Montage ^wNs2S6I8

exemplo de um
solver para alinhar
os pés no chão
usando trace ^Vl3un45g

Control Rig sendo aplicado
depois das poses. No exemplo
é aplicado apenas quando
a velocidade do movimento
é maior que zero ^d6wPdmIg

os bones da skeletal
mesh do character foram
importados ^lSDSGIkU


# Embedded files
7e6e75764bd85491382fe39834f107ef75c93ebd: [[2-UAnimInstancecpp.png]]
54088b811846cdae2e8e31fd3a29a2e46baee393: [[3-props.png]]
6b0c93e47b9b64b5310740de81608539dba65fa2: [[3-memberfuncs.png]]
c4c4813fb9f7c115ca8043f3c6a0c1cfc13e4cb9: [[3-enum.png]]
d6d4a90786ba092acbf5c9aaa595c87df525eb0b: [[4-statemachine.png]]
4f71ba592f37ac6e2b049d471ab5703d1701c8c5: [[4-states.png]]
323e07bc24605d0a6aa6f45daa041db59878a28c: [[4-animgraph.png]]
f5b84fa7f16aa4824ead8ae97b26a4d873e005fc: [[4-animgraphprincipal.png]]
c9d240119ecf2d62951dd3efd668bdaf92c7ed5d: [[6-AnimbpCharacter.png]]
a3b27c18786d2ce9a227af16c74a0b2cc9cde51f: [[7-ControlRigAnimBp.png]]
340715651d4beef365cd49c5f54e611f3706a57d: [[7-ControlrigimportBones.png]]
d32c1bc534a8cc5d8f82e05b65a3e517f4437999: [[7-ControlRigSolver.png]]
15f3975f8854f54cda3e86f788139417b73c6f41: [[8-AnimMontage.png]]
ac45377605e89d180029412bfa7c18cf8a3198a1: [[8-AnimMontageSection.png]]

%%
# Drawing
```json
{
	"type": "excalidraw",
	"version": 2,
	"source": "https://github.com/zsviczian/obsidian-excalidraw-plugin/releases/tag/2.0.3",
	"elements": [
		{
			"type": "text",
			"version": 462,
			"versionNonce": 427616074,
			"isDeleted": false,
			"id": "XAAXgNSX",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -626.8700046389465,
			"y": -584.3926100329342,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 1738.6025390625,
			"height": 99.75378086857228,
			"seed": 2112036942,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1700930556802,
			"link": null,
			"locked": false,
			"fontSize": 79.80302469485783,
			"fontFamily": 1,
			"text": "Como configurar as animações do Character",
			"rawText": "Como configurar as animações do Character",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Como configurar as animações do Character",
			"lineHeight": 1.25,
			"baseline": 70
		},
		{
			"type": "rectangle",
			"version": 585,
			"versionNonce": 1990167126,
			"isDeleted": false,
			"id": "oON4NkWivvKyrP1332JGo",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -916.4306413709772,
			"y": -333.0713191665619,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 536.6324243069159,
			"height": 63.913415790695694,
			"seed": 1702225550,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"type": "text",
					"id": "x1pwMpRQ"
				}
			],
			"updated": 1700930556802,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 611,
			"versionNonce": 1823829514,
			"isDeleted": false,
			"id": "x1pwMpRQ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -776.1942937194724,
			"y": -313.6146112712141,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 256.15972900390625,
			"height": 25,
			"seed": 1398138062,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1700930556802,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Pré-requisitos necessários",
			"rawText": "Pré-requisitos necessários",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "oON4NkWivvKyrP1332JGo",
			"originalText": "Pré-requisitos necessários",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 745,
			"versionNonce": 1982320534,
			"isDeleted": false,
			"id": "ghHn8MKv",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -876.1820459103735,
			"y": -220.7580370994865,
			"strokeColor": "#6741d9",
			"backgroundColor": "transparent",
			"width": 497.1996154785156,
			"height": 175,
			"seed": 2031885070,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1700930556803,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "O skeletal Mesh e rigs do personagem já devem\nter sido importados para o projeto. Além disso o \nBlueprint do Character já deve ter sido criado e\nter a mesh configurada.\n\nMais informações sobre podem ser encontradas\nno How to: ",
			"rawText": "O skeletal Mesh e rigs do personagem já devem\nter sido importados para o projeto. Além disso o \nBlueprint do Character já deve ter sido criado e\nter a mesh configurada.\n\nMais informações sobre podem ser encontradas\nno How to: ",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "O skeletal Mesh e rigs do personagem já devem\nter sido importados para o projeto. Além disso o \nBlueprint do Character já deve ter sido criado e\nter a mesh configurada.\n\nMais informações sobre podem ser encontradas\nno How to: ",
			"lineHeight": 1.25,
			"baseline": 168
		},
		{
			"type": "text",
			"version": 214,
			"versionNonce": 1018109130,
			"isDeleted": false,
			"id": "5SkPckVt",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -980.6463353490801,
			"y": -364.7299555241485,
			"strokeColor": "#6741d9",
			"backgroundColor": "transparent",
			"width": 29.446853637695312,
			"height": 135.83114283942382,
			"seed": 1833011534,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1700930556803,
			"link": null,
			"locked": false,
			"fontSize": 108.66491427153906,
			"fontFamily": 1,
			"text": "1",
			"rawText": "1",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "1",
			"lineHeight": 1.25,
			"baseline": 95
		},
		{
			"type": "rectangle",
			"version": 248,
			"versionNonce": 2130013398,
			"isDeleted": false,
			"id": "ODs-cO7i1ERflWYfoxBEE",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -999.8940132214623,
			"y": -355.742780490301,
			"strokeColor": "#6741d9",
			"backgroundColor": "transparent",
			"width": 672.1199760544978,
			"height": 357.5853722126885,
			"seed": 253702030,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "muUc13lwQnSoJPS2rvrJS",
					"type": "arrow"
				}
			],
			"updated": 1700930556803,
			"link": null,
			"locked": false
		},
		{
			"type": "arrow",
			"version": 740,
			"versionNonce": 654635914,
			"isDeleted": false,
			"id": "muUc13lwQnSoJPS2rvrJS",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -326.53108266354,
			"y": -96.85516901452968,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 132.59164037760613,
			"height": 0.6339148245752426,
			"seed": 1793985998,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1700930556803,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "ODs-cO7i1ERflWYfoxBEE",
				"focus": 0.4529497021137924,
				"gap": 1.2429545034243574
			},
			"endBinding": {
				"elementId": "gdrsNBrKR6EcrWy3r_g9P",
				"focus": 0.18332855726572253,
				"gap": 9.015453687309275
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					132.59164037760613,
					-0.6339148245752426
				]
			]
		},
		{
			"type": "text",
			"version": 221,
			"versionNonce": 1855808022,
			"isDeleted": false,
			"id": "8RMfLITa",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -760.1641220538428,
			"y": -61.88891205499317,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 312.70074462890625,
			"height": 25,
			"seed": 2211,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1700930556803,
			"link": "[[Como criar um Character]]",
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "📍[[Como criar um Character]]",
			"rawText": "[[Como criar um Character]]",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "📍[[Como criar um Character]]",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "rectangle",
			"version": 721,
			"versionNonce": 1576137290,
			"isDeleted": false,
			"id": "s_81Geho7Xmjv2WO0uyPO",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -74.83127684975682,
			"y": -329.99886364977067,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 536.6324243069159,
			"height": 63.913415790695694,
			"seed": 67773710,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"type": "text",
					"id": "tWqoaXCV"
				}
			],
			"updated": 1700930556803,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 799,
			"versionNonce": 672444246,
			"isDeleted": false,
			"id": "tWqoaXCV",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -10.824909667001975,
			"y": -310.5421557544228,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 408.61968994140625,
			"height": 25,
			"seed": 1105089358,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1700930556803,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Criar classe que herda de UAnimInstance",
			"rawText": "Criar classe que herda de UAnimInstance",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "s_81Geho7Xmjv2WO0uyPO",
			"originalText": "Criar classe que herda de UAnimInstance",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 1293,
			"versionNonce": 340859146,
			"isDeleted": false,
			"id": "MYGjA3JU",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -64.12106780742226,
			"y": -218.91633203341632,
			"strokeColor": "#0c8599",
			"backgroundColor": "transparent",
			"width": 538.6195068359375,
			"height": 200,
			"seed": 160610702,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1700930556803,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Criar um classe que herda de UAnimInstance para\nutilizarmos como pai do nosso Animation blueprint.\nIsso nos possibilita guardarmos variáveis relacionadas\nas animações e criarmos outras personalizações \nem C++. Nela já fazemos override nas duas principais\nmembers functions herdadas que é a que executa na\ninicialização da animção e a outra a cada tick de \nupdate.",
			"rawText": "Criar um classe que herda de UAnimInstance para\nutilizarmos como pai do nosso Animation blueprint.\nIsso nos possibilita guardarmos variáveis relacionadas\nas animações e criarmos outras personalizações \nem C++. Nela já fazemos override nas duas principais\nmembers functions herdadas que é a que executa na\ninicialização da animção e a outra a cada tick de \nupdate.",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Criar um classe que herda de UAnimInstance para\nutilizarmos como pai do nosso Animation blueprint.\nIsso nos possibilita guardarmos variáveis relacionadas\nas animações e criarmos outras personalizações \nem C++. Nela já fazemos override nas duas principais\nmembers functions herdadas que é a que executa na\ninicialização da animção e a outra a cada tick de \nupdate.",
			"lineHeight": 1.25,
			"baseline": 193
		},
		{
			"type": "text",
			"version": 316,
			"versionNonce": 1739609238,
			"isDeleted": false,
			"id": "F828TvMs",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -165.6763107262425,
			"y": -360.4266556563957,
			"strokeColor": "#0c8599",
			"backgroundColor": "transparent",
			"width": 77.36592102050781,
			"height": 135.83114283942382,
			"seed": 576739278,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1700930556803,
			"link": null,
			"locked": false,
			"fontSize": 108.66491427153906,
			"fontFamily": 1,
			"text": "2",
			"rawText": "2",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "2",
			"lineHeight": 1.25,
			"baseline": 95
		},
		{
			"type": "rectangle",
			"version": 446,
			"versionNonce": 1771923402,
			"isDeleted": false,
			"id": "gdrsNBrKR6EcrWy3r_g9P",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -184.92398859862465,
			"y": -351.4394806225482,
			"strokeColor": "#0c8599",
			"backgroundColor": "transparent",
			"width": 690.5815145160362,
			"height": 618.5085054759097,
			"seed": 73412110,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "muUc13lwQnSoJPS2rvrJS",
					"type": "arrow"
				},
				{
					"id": "VHyjubsSq6O15yjYlI7LQ",
					"type": "arrow"
				}
			],
			"updated": 1700930556803,
			"link": null,
			"locked": false
		},
		{
			"type": "image",
			"version": 269,
			"versionNonce": 388321750,
			"isDeleted": false,
			"id": "2howcy2IPo6_iVu_rr8sb",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -155.35025186890607,
			"y": 30.97304111288804,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 634.2305438701924,
			"height": 199.84672309821758,
			"seed": 1739930766,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1700930556803,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "7e6e75764bd85491382fe39834f107ef75c93ebd",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "rectangle",
			"version": 831,
			"versionNonce": 3410826,
			"isDeleted": false,
			"id": "lUFOFH3vb4eKSTRv70URj",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 831.937803679089,
			"y": -333.07802050676,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 536.6324243069159,
			"height": 63.913415790695694,
			"seed": 2076950610,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"type": "text",
					"id": "ervMy29b"
				}
			],
			"updated": 1700930939518,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 948,
			"versionNonce": 1904085578,
			"isDeleted": false,
			"id": "ervMy29b",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 916.2341946655548,
			"y": -313.6213126114122,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 368.0396423339844,
			"height": 25,
			"seed": 148104722,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1700930939518,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Configurar as variáveis já existentes",
			"rawText": "Configurar as variáveis já existentes",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "lUFOFH3vb4eKSTRv70URj",
			"originalText": "Configurar as variáveis já existentes",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 1661,
			"versionNonce": 369720650,
			"isDeleted": false,
			"id": "1QsX4lkt",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 842.6480127214234,
			"y": -221.99548889040568,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 567.01953125,
			"height": 125,
			"seed": 357651410,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1700930556803,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Caso já existam variáveis possíveis elas já podem ser\ncriadas na classe C++ para que sejam herdadas pelo\nblueprint. Outra prática aconselhável é controlar os \nestados das animações nesta classe com enums criados \nem uma classe header específica.",
			"rawText": "Caso já existam variáveis possíveis elas já podem ser\ncriadas na classe C++ para que sejam herdadas pelo\nblueprint. Outra prática aconselhável é controlar os \nestados das animações nesta classe com enums criados \nem uma classe header específica.",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Caso já existam variáveis possíveis elas já podem ser\ncriadas na classe C++ para que sejam herdadas pelo\nblueprint. Outra prática aconselhável é controlar os \nestados das animações nesta classe com enums criados \nem uma classe header específica.",
			"lineHeight": 1.25,
			"baseline": 118
		},
		{
			"type": "text",
			"version": 391,
			"versionNonce": 1196381270,
			"isDeleted": false,
			"id": "iK33tpYT",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 738.1837232827168,
			"y": -363.5058125133851,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 73.99745178222656,
			"height": 135.83114283942382,
			"seed": 324733330,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1700930556803,
			"link": null,
			"locked": false,
			"fontSize": 108.66491427153906,
			"fontFamily": 1,
			"text": "3",
			"rawText": "3",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "3",
			"lineHeight": 1.25,
			"baseline": 95
		},
		{
			"type": "rectangle",
			"version": 849,
			"versionNonce": 390022154,
			"isDeleted": false,
			"id": "cBofnxhXqmKFZiUzbKOZr",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 718.9361267905429,
			"y": -358.78532042224583,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 1313.5149455056194,
			"height": 961.9751395904927,
			"seed": 438830930,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "VHyjubsSq6O15yjYlI7LQ",
					"type": "arrow"
				},
				{
					"id": "2gxzjw7ckVIqcdk3qlMwI",
					"type": "arrow"
				}
			],
			"updated": 1700930556803,
			"link": null,
			"locked": false
		},
		{
			"type": "arrow",
			"version": 1595,
			"versionNonce": 1917737366,
			"isDeleted": false,
			"id": "VHyjubsSq6O15yjYlI7LQ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 517.6212630128819,
			"y": -3.6918734119935985,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 195.50099022372342,
			"height": 3.0179123469161064,
			"seed": 187694122,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1700930556803,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "gdrsNBrKR6EcrWy3r_g9P",
				"focus": 0.10477341266963018,
				"gap": 11.963737095470265
			},
			"endBinding": {
				"elementId": "2DHGo4VlGkgDjcblE3uyK",
				"focus": 0.8994397678531948,
				"gap": 23.979887989737733
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					195.50099022372342,
					3.0179123469161064
				]
			]
		},
		{
			"type": "image",
			"version": 221,
			"versionNonce": 1670263498,
			"isDeleted": false,
			"id": "Yxz48J3jWkQjS83J0I1IA",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1444.08685896222,
			"y": -342.58662440402236,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 570.2533287338064,
			"height": 318.0000915527344,
			"seed": 573989674,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1700930556803,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "54088b811846cdae2e8e31fd3a29a2e46baee393",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 371,
			"versionNonce": 163231446,
			"isDeleted": false,
			"id": "2DHGo4VlGkgDjcblE3uyK",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 737.102141226343,
			"y": -10.627673676608651,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 802.7218934911248,
			"height": 439.3846153846157,
			"seed": 1501948522,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "VHyjubsSq6O15yjYlI7LQ",
					"type": "arrow"
				},
				{
					"id": "_LyYQ06Tb5nJf9VX4mXVZ",
					"type": "arrow"
				}
			],
			"updated": 1700930556803,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "6b0c93e47b9b64b5310740de81608539dba65fa2",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 456,
			"versionNonce": 227625354,
			"isDeleted": false,
			"id": "0OAqVJ8F51-x19wz9tR0o",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1236.2520991277354,
			"y": 436.2389332069049,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 739.9999999999997,
			"height": 156.25498007968122,
			"seed": 1151926122,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1700930556803,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "c4c4813fb9f7c115ca8043f3c6a0c1cfc13e4cb9",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "rectangle",
			"version": 962,
			"versionNonce": 1177119766,
			"isDeleted": false,
			"id": "Hcc81h-4olskvofj95kBQ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -964.2410941860853,
			"y": 142.7464368826386,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 536.6324243069159,
			"height": 63.913415790695694,
			"seed": 1855541610,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"type": "text",
					"id": "TqBIuinO"
				}
			],
			"updated": 1700930556803,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 1118,
			"versionNonce": 478382154,
			"isDeleted": false,
			"id": "TqBIuinO",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -948.0246745130961,
			"y": 162.20314477798644,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 504.1995849609375,
			"height": 25,
			"seed": 1392481322,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1700930556803,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Criar Animation Blueprint para gerenciar os states",
			"rawText": "Criar Animation Blueprint para gerenciar os states",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "Hcc81h-4olskvofj95kBQ",
			"originalText": "Criar Animation Blueprint para gerenciar os states",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 1865,
			"versionNonce": 93288790,
			"isDeleted": false,
			"id": "R2V2ZOHa",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -963.7127699093758,
			"y": 233.46575383280015,
			"strokeColor": "#9c36b5",
			"backgroundColor": "transparent",
			"width": 565.2595825195312,
			"height": 125,
			"seed": 1057980138,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1700930556803,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Para manter o AnimGraph do nosso blueprint organizado\npodemos criar opcionalmente mais um Animation blueprint\ne salvar apenas as states machines nela. Podemos criar\nquantos foram necessárias. Depois basta linkar todos\nAnimation Blueprint no Blueprint principal.",
			"rawText": "Para manter o AnimGraph do nosso blueprint organizado\npodemos criar opcionalmente mais um Animation blueprint\ne salvar apenas as states machines nela. Podemos criar\nquantos foram necessárias. Depois basta linkar todos\nAnimation Blueprint no Blueprint principal.",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Para manter o AnimGraph do nosso blueprint organizado\npodemos criar opcionalmente mais um Animation blueprint\ne salvar apenas as states machines nela. Podemos criar\nquantos foram necessárias. Depois basta linkar todos\nAnimation Blueprint no Blueprint principal.",
			"lineHeight": 1.25,
			"baseline": 118
		},
		{
			"type": "text",
			"version": 560,
			"versionNonce": 2017455882,
			"isDeleted": false,
			"id": "E0OWnp23",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1055.086128062571,
			"y": 113.77339008197998,
			"strokeColor": "#9c36b5",
			"backgroundColor": "transparent",
			"width": 67.15188598632812,
			"height": 135.83114283942382,
			"seed": 1599345066,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1700930556803,
			"link": null,
			"locked": false,
			"fontSize": 108.66491427153906,
			"fontFamily": 1,
			"text": "5",
			"rawText": "5",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "5",
			"lineHeight": 1.25,
			"baseline": 95
		},
		{
			"type": "rectangle",
			"version": 832,
			"versionNonce": 524410518,
			"isDeleted": false,
			"id": "tCmvMLPDhxuGz-LK6fiRd",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1205.242896844044,
			"y": 118.39710630900925,
			"strokeColor": "#9c36b5",
			"backgroundColor": "transparent",
			"width": 882.5814701268315,
			"height": 574.872141839546,
			"seed": 385371242,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "HIo_0qVjjnZwqgpOxap8g",
					"type": "arrow"
				},
				{
					"id": "9Bz_wW9xJ50c7LeTu-Jp7",
					"type": "arrow"
				}
			],
			"updated": 1700930556803,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 1013,
			"versionNonce": 1430355402,
			"isDeleted": false,
			"id": "vvP2dFvf6dCQDUs4n5Fsn",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -77.62265639015413,
			"y": 342.0679478911612,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 536.6324243069159,
			"height": 63.913415790695694,
			"seed": 653197418,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"type": "text",
					"id": "7G9h5KHx"
				}
			],
			"updated": 1700930556803,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 1209,
			"versionNonce": 938843094,
			"isDeleted": false,
			"id": "7G9h5KHx",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -66.98622328943054,
			"y": 361.5246557865091,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 515.3595581054688,
			"height": 25,
			"seed": 1925669674,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1700930556803,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Criar Animation Blueprint herdando da classe criada",
			"rawText": "Criar Animation Blueprint herdando da classe criada",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "vvP2dFvf6dCQDUs4n5Fsn",
			"originalText": "Criar Animation Blueprint herdando da classe criada",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 1978,
			"versionNonce": 547566730,
			"isDeleted": false,
			"id": "N2WUOrxW",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 148.36010236808943,
			"y": 438.60524690808427,
			"strokeColor": "#c2255c",
			"backgroundColor": "transparent",
			"width": 365.75970458984375,
			"height": 175,
			"seed": 1392864746,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1700930556803,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Criar BP herdando da classe criada,\ncriar e configurar as state machines\nnecessárias no AnimGraph. Para \nfacilitar a organização elas podem \nser salvas em cache e encadeadas \npara serem conecta na pose de \noutput.",
			"rawText": "Criar BP herdando da classe criada,\ncriar e configurar as state machines\nnecessárias no AnimGraph. Para \nfacilitar a organização elas podem \nser salvas em cache e encadeadas \npara serem conecta na pose de \noutput.",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Criar BP herdando da classe criada,\ncriar e configurar as state machines\nnecessárias no AnimGraph. Para \nfacilitar a organização elas podem \nser salvas em cache e encadeadas \npara serem conecta na pose de \noutput.",
			"lineHeight": 1.25,
			"baseline": 168
		},
		{
			"type": "text",
			"version": 612,
			"versionNonce": 364884246,
			"isDeleted": false,
			"id": "prNmWgCp",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -168.46769026663992,
			"y": 314.54942435044563,
			"strokeColor": "#c2255c",
			"backgroundColor": "transparent",
			"width": 69.54240417480469,
			"height": 135.83114283942382,
			"seed": 2092179626,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1700930556803,
			"link": null,
			"locked": false,
			"fontSize": 108.66491427153906,
			"fontFamily": 1,
			"text": "4",
			"rawText": "4",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "4",
			"lineHeight": 1.25,
			"baseline": 95
		},
		{
			"type": "rectangle",
			"version": 1006,
			"versionNonce": 1814041418,
			"isDeleted": false,
			"id": "61SNH5OxPceg5f0zR61cf",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -185.1940021352343,
			"y": 321.4032172228349,
			"strokeColor": "#c2255c",
			"backgroundColor": "transparent",
			"width": 801.2240482518317,
			"height": 976.3267760725,
			"seed": 1266580330,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "2gxzjw7ckVIqcdk3qlMwI",
					"type": "arrow"
				},
				{
					"id": "HIo_0qVjjnZwqgpOxap8g",
					"type": "arrow"
				}
			],
			"updated": 1700930556803,
			"link": null,
			"locked": false
		},
		{
			"type": "image",
			"version": 303,
			"versionNonce": 1947541078,
			"isDeleted": false,
			"id": "JGmYyEwoTHVih9A55jzKL",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -166.1976044889584,
			"y": 443.2970426593022,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 297,
			"height": 170,
			"seed": 1167022314,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1700930556803,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "d6d4a90786ba092acbf5c9aaa595c87df525eb0b",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 329,
			"versionNonce": 1511201290,
			"isDeleted": false,
			"id": "iKmW74G_2B0zSwyFczs20",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -150.42467746481066,
			"y": 641.7971314377105,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 632,
			"height": 205,
			"seed": 1507275690,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1700930556803,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "4f71ba592f37ac6e2b049d471ab5703d1701c8c5",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 615,
			"versionNonce": 1472914326,
			"isDeleted": false,
			"id": "oWMeZUmSya4Ch50LeHMX0",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -120.24279269918543,
			"y": 864.3795267295804,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 517.0909978693182,
			"height": 407.5378203546322,
			"seed": 1518366186,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "7LGdoFGWDF3Zo81VARaVz",
					"type": "arrow"
				}
			],
			"updated": 1700930556803,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "323e07bc24605d0a6aa6f45daa041db59878a28c",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 2321,
			"versionNonce": 158812362,
			"isDeleted": false,
			"id": "2gxzjw7ckVIqcdk3qlMwI",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 702.2978091941607,
			"y": 477.7935058573467,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 77.08073030184448,
			"height": 0.826507619114011,
			"seed": 1108840618,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1700930556803,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "cBofnxhXqmKFZiUzbKOZr",
				"gap": 16.638317596381967,
				"focus": -0.7105139480425464
			},
			"endBinding": {
				"elementId": "61SNH5OxPceg5f0zR61cf",
				"gap": 9.187032775718649,
				"focus": -0.6631059054582309
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-77.08073030184448,
					0.826507619114011
				]
			]
		},
		{
			"type": "image",
			"version": 389,
			"versionNonce": 1662386390,
			"isDeleted": false,
			"id": "Zqbl5acxECiAA8H1R6T4F",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1182.0428045363055,
			"y": 395.5210305854382,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 834,
			"height": 272,
			"seed": 1392608054,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1700930556803,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "f5b84fa7f16aa4824ead8ae97b26a4d873e005fc",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 2499,
			"versionNonce": 31956874,
			"isDeleted": false,
			"id": "HIo_0qVjjnZwqgpOxap8g",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -189.65358462686257,
			"y": 402.26923025835504,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 125.27477770951444,
			"height": 5.465362152238754,
			"seed": 1971479414,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1700930556803,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "61SNH5OxPceg5f0zR61cf",
				"gap": 4.4595824916281686,
				"focus": 0.8410287173032089
			},
			"endBinding": {
				"elementId": "tCmvMLPDhxuGz-LK6fiRd",
				"gap": 7.733064380835572,
				"focus": 0.07007433031199889
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-125.27477770951444,
					5.465362152238754
				]
			]
		},
		{
			"type": "rectangle",
			"version": 1302,
			"versionNonce": 697005590,
			"isDeleted": false,
			"id": "wAWhi4ZMHp36-YPPGy7aA",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1082.6405674341893,
			"y": 798.4797095507224,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 722.8142868779387,
			"height": 72.64066632336619,
			"seed": 633713450,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"type": "text",
					"id": "97WV76UN"
				}
			],
			"updated": 1700930556803,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 1565,
			"versionNonce": 530521674,
			"isDeleted": false,
			"id": "97WV76UN",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -936.6532543174856,
			"y": 822.3000427124055,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 430.83966064453125,
			"height": 25,
			"seed": 834256362,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1700930556803,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Atribuir o Animation Blueprint ao Character",
			"rawText": "Atribuir o Animation Blueprint ao Character",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "wAWhi4ZMHp36-YPPGy7aA",
			"originalText": "Atribuir o Animation Blueprint ao Character",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 2272,
			"versionNonce": 69223254,
			"isDeleted": false,
			"id": "0mDKK3te",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1010.4516208208322,
			"y": 925.5627738375315,
			"strokeColor": "#099268",
			"backgroundColor": "transparent",
			"width": 653.2594604492188,
			"height": 50,
			"seed": 543060138,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1700930556803,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Com o Animation Blueprint pronto basta agora atribuir o blueprint\nao Character para ele usar as animações configuradas.",
			"rawText": "Com o Animation Blueprint pronto basta agora atribuir o blueprint\nao Character para ele usar as animações configuradas.",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Com o Animation Blueprint pronto basta agora atribuir o blueprint\nao Character para ele usar as animações configuradas.",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "text",
			"version": 845,
			"versionNonce": 2138621194,
			"isDeleted": false,
			"id": "sIbBfYxs",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1183.2795022339703,
			"y": 775.3247557898363,
			"strokeColor": "#099268",
			"backgroundColor": "transparent",
			"width": 69.54240417480469,
			"height": 135.83114283942382,
			"seed": 626969450,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1700930556803,
			"link": null,
			"locked": false,
			"fontSize": 108.66491427153906,
			"fontFamily": 1,
			"text": "6",
			"rawText": "6",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "6",
			"lineHeight": 1.25,
			"baseline": 95
		},
		{
			"type": "rectangle",
			"version": 1096,
			"versionNonce": 1697212566,
			"isDeleted": false,
			"id": "PQqzTpy_CuiWcXI2vHXrl",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1202.5271801063527,
			"y": 774.1304899501043,
			"strokeColor": "#099268",
			"backgroundColor": "transparent",
			"width": 882.5814701268315,
			"height": 398.872141839546,
			"seed": 1191562794,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "9Bz_wW9xJ50c7LeTu-Jp7",
					"type": "arrow"
				},
				{
					"id": "ZGUfQLbypc6C-fCFI3S_k",
					"type": "arrow"
				}
			],
			"updated": 1700930556803,
			"link": null,
			"locked": false
		},
		{
			"type": "arrow",
			"version": 2376,
			"versionNonce": 1794085834,
			"isDeleted": false,
			"id": "9Bz_wW9xJ50c7LeTu-Jp7",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -749.2848450285089,
			"y": 700.2615532242537,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 1.945072107288297,
			"height": 65.39567822883441,
			"seed": 1140385770,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1700930556803,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "tCmvMLPDhxuGz-LK6fiRd",
				"gap": 6.992305075698482,
				"focus": -0.05248045056398626
			},
			"endBinding": {
				"elementId": "PQqzTpy_CuiWcXI2vHXrl",
				"gap": 8.473258497016161,
				"focus": 0.008547542011508188
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-1.945072107288297,
					65.39567822883441
				]
			]
		},
		{
			"type": "image",
			"version": 307,
			"versionNonce": 744220118,
			"isDeleted": false,
			"id": "lIJnmI4INIXOtkl95H0ho",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1139.2378423165526,
			"y": 1030.580228570415,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 782,
			"height": 79.20810313075506,
			"seed": 130940630,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1700930556803,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "c9d240119ecf2d62951dd3efd668bdaf92c7ed5d",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "rectangle",
			"version": 1793,
			"versionNonce": 1142852234,
			"isDeleted": false,
			"id": "AXGvM5fsbs4dKQg0UH4Db",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1076.9856208075653,
			"y": 1376.4056482484934,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 722.8142868779387,
			"height": 72.64066632336619,
			"seed": 1381374794,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"type": "text",
					"id": "H7dtWtLJ"
				}
			],
			"updated": 1700930556803,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 2124,
			"versionNonce": 2060237590,
			"isDeleted": false,
			"id": "H7dtWtLJ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -925.5282912113694,
			"y": 1400.2259814101765,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 419.8996276855469,
			"height": 25,
			"seed": 474489354,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1700930556803,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Criar blueprint de Control Rig caso preciso",
			"rawText": "Criar blueprint de Control Rig caso preciso",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "AXGvM5fsbs4dKQg0UH4Db",
			"originalText": "Criar blueprint de Control Rig caso preciso",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 3287,
			"versionNonce": 1908451658,
			"isDeleted": false,
			"id": "VjmNsIyb",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -260.18110177834296,
			"y": 1392.5553691859434,
			"strokeColor": "#e8590c",
			"backgroundColor": "transparent",
			"width": 677.7593383789062,
			"height": 175,
			"seed": 1338724554,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1700930556803,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Se houverem personalizações que deseja fazer nas animações como\npor exemplo alinhar os pés em superfícies irregulares os Control\nRigs podem ser usados. Você deve cria-los e importar o rig da \nskeletal mesh do personagem e criar solvers para fazer os cálculos.\nPara que o control rig seja considerado na animação ele deve ser\nreferenciado no Animation Blueprint e aplicado depois das poses de\nanimação.",
			"rawText": "Se houverem personalizações que deseja fazer nas animações como\npor exemplo alinhar os pés em superfícies irregulares os Control\nRigs podem ser usados. Você deve cria-los e importar o rig da \nskeletal mesh do personagem e criar solvers para fazer os cálculos.\nPara que o control rig seja considerado na animação ele deve ser\nreferenciado no Animation Blueprint e aplicado depois das poses de\nanimação.",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Se houverem personalizações que deseja fazer nas animações como\npor exemplo alinhar os pés em superfícies irregulares os Control\nRigs podem ser usados. Você deve cria-los e importar o rig da \nskeletal mesh do personagem e criar solvers para fazer os cálculos.\nPara que o control rig seja considerado na animação ele deve ser\nreferenciado no Animation Blueprint e aplicado depois das poses de\nanimação.",
			"lineHeight": 1.25,
			"baseline": 168
		},
		{
			"type": "text",
			"version": 1355,
			"versionNonce": 116451414,
			"isDeleted": false,
			"id": "u4KfXBfn",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1178.6912059979713,
			"y": 1366.050824695941,
			"strokeColor": "#e8590c",
			"backgroundColor": "transparent",
			"width": 58.459075927734375,
			"height": 135.83114283942382,
			"seed": 1887086474,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1700930556803,
			"link": null,
			"locked": false,
			"fontSize": 108.66491427153906,
			"fontFamily": 1,
			"text": "7",
			"rawText": "7",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "7",
			"lineHeight": 1.25,
			"baseline": 95
		},
		{
			"type": "rectangle",
			"version": 1876,
			"versionNonce": 1261498378,
			"isDeleted": false,
			"id": "8TvO9o2q9qwZG_wA3VPIl",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1196.8722334797285,
			"y": 1353.123160418709,
			"strokeColor": "#e8590c",
			"backgroundColor": "transparent",
			"width": 1661.6584307638507,
			"height": 1001.9488771159877,
			"seed": 1452353098,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "ZGUfQLbypc6C-fCFI3S_k",
					"type": "arrow"
				},
				{
					"id": "UtOCWbv2uhCwqv6H6FYE3",
					"type": "arrow"
				}
			],
			"updated": 1700930556803,
			"link": null,
			"locked": false
		},
		{
			"type": "arrow",
			"version": 3280,
			"versionNonce": 1889365398,
			"isDeleted": false,
			"id": "ZGUfQLbypc6C-fCFI3S_k",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -656.6830941713841,
			"y": 1178.4460213807151,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0.41814151176708947,
			"height": 166.4828489519914,
			"seed": 745554250,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1700930556803,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "PQqzTpy_CuiWcXI2vHXrl",
				"gap": 5.443389591064772,
				"focus": -0.23548994447621388
			},
			"endBinding": {
				"elementId": "8TvO9o2q9qwZG_wA3VPIl",
				"gap": 8.194290086002297,
				"focus": -0.3472508675160037
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					0.41814151176708947,
					166.4828489519914
				]
			]
		},
		{
			"type": "image",
			"version": 763,
			"versionNonce": 74079946,
			"isDeleted": false,
			"id": "VNbVuwqDsIkhvLlDHHOPf",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -635.9342986922097,
			"y": 1907.5035954929197,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 875.0769981971154,
			"height": 326.9384896042,
			"seed": 1916507402,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1700930556803,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "a3b27c18786d2ce9a227af16c74a0b2cc9cde51f",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 248,
			"versionNonce": 352799446,
			"isDeleted": false,
			"id": "dC4bBpP6bG6QmhTN8NkY0",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1128.5497772078343,
			"y": 1486.3494512058105,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 370.7263533045276,
			"height": 813.5383864182689,
			"seed": 944289494,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1700930556803,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "340715651d4beef365cd49c5f54e611f3706a57d",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 587,
			"versionNonce": 595809802,
			"isDeleted": false,
			"id": "OVSVM-hPvxYWVNWZ4Ear_",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -697.7803774181707,
			"y": 1523.0100729140847,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 375.9411881978253,
			"height": 269.6855884780233,
			"seed": 620495114,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "-EH0RDo_5dDGQT34oYhWM",
					"type": "arrow"
				}
			],
			"updated": 1700930829593,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "d32c1bc534a8cc5d8f82e05b65a3e517f4437999",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "rectangle",
			"version": 1653,
			"versionNonce": 1656979478,
			"isDeleted": false,
			"id": "eT4F28EsNGdbjjQhpg5e9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 844.333385056362,
			"y": 763.6061515223964,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 722.8142868779387,
			"height": 72.64066632336619,
			"seed": 494195798,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"type": "text",
					"id": "myP4g2t2"
				}
			],
			"updated": 1700930556803,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 1962,
			"versionNonce": 1027912778,
			"isDeleted": false,
			"id": "myP4g2t2",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 989.8807109904485,
			"y": 787.4264846840795,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 431.7196350097656,
			"height": 25,
			"seed": 1740888470,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1700930556803,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Criar Animation Montages caso seja preciso",
			"rawText": "Criar Animation Montages caso seja preciso",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "eT4F28EsNGdbjjQhpg5e9",
			"originalText": "Criar Animation Montages caso seja preciso",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 2877,
			"versionNonce": 768019798,
			"isDeleted": false,
			"id": "6ilIAJUf",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 763.9072099750076,
			"y": 878.6122892110232,
			"strokeColor": "#9c36b5",
			"backgroundColor": "transparent",
			"width": 665.0794677734375,
			"height": 150,
			"seed": 880817878,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1700930556803,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Caso precise de um controle mais preciso de animações como \nvariações da mesma animação, encadear duas ou mais animações\nemitir diversos notifies dessas animações encadeadas as Animation\nMontages ncessárias devem ser criadas.\n\n",
			"rawText": "Caso precise de um controle mais preciso de animações como \nvariações da mesma animação, encadear duas ou mais animações\nemitir diversos notifies dessas animações encadeadas as Animation\nMontages ncessárias devem ser criadas.\n\n",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Caso precise de um controle mais preciso de animações como \nvariações da mesma animação, encadear duas ou mais animações\nemitir diversos notifies dessas animações encadeadas as Animation\nMontages ncessárias devem ser criadas.\n\n",
			"lineHeight": 1.25,
			"baseline": 143
		},
		{
			"type": "text",
			"version": 1171,
			"versionNonce": 1073453834,
			"isDeleted": false,
			"id": "1hGCGaPw",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 738.607360913632,
			"y": 741.1896355119109,
			"strokeColor": "#9c36b5",
			"backgroundColor": "transparent",
			"width": 83.12490844726562,
			"height": 135.83114283942382,
			"seed": 2084498454,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1700930556803,
			"link": null,
			"locked": false,
			"fontSize": 108.66491427153906,
			"fontFamily": 1,
			"text": "8",
			"rawText": "8",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "8",
			"lineHeight": 1.25,
			"baseline": 95
		},
		{
			"type": "rectangle",
			"version": 1780,
			"versionNonce": 57078422,
			"isDeleted": false,
			"id": "NExMtpdZk6UbxnN9qmMHv",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 720.9185397119222,
			"y": 730.6415848664898,
			"strokeColor": "#9c36b5",
			"backgroundColor": "transparent",
			"width": 1517.6586561244271,
			"height": 691.7951624224783,
			"seed": 1559558486,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "UtOCWbv2uhCwqv6H6FYE3",
					"type": "arrow"
				}
			],
			"updated": 1700930556803,
			"link": null,
			"locked": false
		},
		{
			"type": "image",
			"version": 248,
			"versionNonce": 311663702,
			"isDeleted": false,
			"id": "oZrY8f5G1lsVIIAXNkNkD",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 753.4091925605308,
			"y": 1055.4264065763402,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 1440,
			"height": 215,
			"seed": 1535624074,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "ZYlvhLFFmdV5Ux8sFice8",
					"type": "arrow"
				}
			],
			"updated": 1700930746179,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "15f3975f8854f54cda3e86f788139417b73c6f41",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 299,
			"versionNonce": 2119708630,
			"isDeleted": false,
			"id": "SUQyAlkI2LFGmbr-4KbUf",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1677.5160365357124,
			"y": 784.0225308574815,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 426,
			"height": 228,
			"seed": 1859669014,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1700930556803,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "ac45377605e89d180029412bfa7c18cf8a3198a1",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 2414,
			"versionNonce": 1449386122,
			"isDeleted": false,
			"id": "UtOCWbv2uhCwqv6H6FYE3",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 469.81555383006486,
			"y": 1386.0867347258713,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 246.6933957999177,
			"height": 1.9355251523625157,
			"seed": 1054829206,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1700930556803,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "8TvO9o2q9qwZG_wA3VPIl",
				"focus": -0.9180319038010151,
				"gap": 5.029356545942505
			},
			"endBinding": {
				"elementId": "NExMtpdZk6UbxnN9qmMHv",
				"focus": -0.857247939155495,
				"gap": 4.409590081939655
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					246.6933957999177,
					-1.9355251523625157
				]
			]
		},
		{
			"id": "8RZMON3P",
			"type": "text",
			"x": 1569.1889833273449,
			"y": 30.169866374675394,
			"width": 437.41961669921875,
			"height": 75,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 687350614,
			"version": 1383,
			"versionNonce": 447726870,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "mRi8A2bUQGViWjNC8kyH4",
					"type": "arrow"
				}
			],
			"updated": 1700930556803,
			"link": null,
			"locked": false,
			"text": "Guardar o CharacterMovementComponent\nnos permite a ter acesso a dados \nimportantes do movimento como a velocidade",
			"rawText": "Guardar o CharacterMovementComponent\nnos permite a ter acesso a dados \nimportantes do movimento como a velocidade",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 68,
			"containerId": null,
			"originalText": "Guardar o CharacterMovementComponent\nnos permite a ter acesso a dados \nimportantes do movimento como a velocidade",
			"lineHeight": 1.25
		},
		{
			"id": "mRi8A2bUQGViWjNC8kyH4",
			"type": "arrow",
			"x": 1552.6823417723963,
			"y": 52.4638547708156,
			"width": 119.02271276490455,
			"height": 84.05905330882263,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 357719318,
			"version": 473,
			"versionNonce": 2095791946,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1700930556803,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-44.66982903328699,
					21.941420611212493
				],
				[
					-78.5523830314487,
					42.64727424172713
				],
				[
					-119.02271276490455,
					84.05905330882263
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "8RZMON3P",
				"focus": 0.9021166091646983,
				"gap": 16.5066415549486
			},
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"type": "arrow",
			"version": 600,
			"versionNonce": 165851734,
			"isDeleted": false,
			"id": "_LyYQ06Tb5nJf9VX4mXVZ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1661.8251319647065,
			"y": 128.41050385171144,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 117.14024493402212,
			"height": 212.05903894760934,
			"seed": 2069051478,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1700930556803,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "2DHGo4VlGkgDjcblE3uyK",
				"focus": 0.8527999056384943,
				"gap": 4.860852313216526
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-11.695058334053101,
					66.46531668197093
				],
				[
					-49.37571138622843,
					152.7649643841903
				],
				[
					-117.14024493402212,
					212.05903894760934
				]
			]
		},
		{
			"type": "text",
			"version": 1558,
			"versionNonce": 10012170,
			"isDeleted": false,
			"id": "xu1Yhm4L",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1690.4787441413382,
			"y": 287.7288909610721,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 303.13983154296875,
			"height": 75,
			"seed": 1886245974,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1700930556803,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Enum para gerenciar estados\najuda a criar a lógica que vai\ndisparar as animações",
			"rawText": "Enum para gerenciar estados\najuda a criar a lógica que vai\ndisparar as animações",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Enum para gerenciar estados\najuda a criar a lógica que vai\ndisparar as animações",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "arrow",
			"version": 714,
			"versionNonce": 113637270,
			"isDeleted": false,
			"id": "q16Bb-OhyGZE93UHE4s6T",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1772.9528558003342,
			"y": 385.73403306695104,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 197.14024493402235,
			"height": 85.94137752757263,
			"seed": 1535314902,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1700930556803,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-46.55200963990478,
					37.941391888785915
				],
				[
					-119.9640902924782,
					69.9414062499992
				],
				[
					-197.14024493402235,
					85.94137752757263
				]
			]
		},
		{
			"id": "EqVHMFB-N39uTRaVZB0Sc",
			"type": "rectangle",
			"x": -1185.8554878791083,
			"y": 397.98442428918815,
			"width": 186.66674804687477,
			"height": 105.60001627604163,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"seed": 1328853206,
			"version": 65,
			"versionNonce": 711423178,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1700930556803,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 129,
			"versionNonce": 697210070,
			"isDeleted": false,
			"id": "yW_tDiSt8_TSKiNAnLEa_",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -940.255512293171,
			"y": 519.051115369917,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 186.66674804687477,
			"height": 105.60001627604163,
			"seed": 609634506,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1700930556803,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 206,
			"versionNonce": 1811041162,
			"isDeleted": false,
			"id": "bbu_er41_bjt708ACAd_W",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -66.38897583484004,
			"y": 867.85124557825,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 405.3334147135415,
			"height": 198.3999837239583,
			"seed": 1016538314,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "7LGdoFGWDF3Zo81VARaVz",
					"type": "arrow"
				}
			],
			"updated": 1700930556803,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 1626,
			"versionNonce": 1003588118,
			"isDeleted": false,
			"id": "OcE0bwha",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 421.6402369453526,
			"y": 871.2489838803864,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 184.1998748779297,
			"height": 25,
			"seed": 1611254358,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1700930556803,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Salvando em cache",
			"rawText": "Salvando em cache",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Salvando em cache",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "arrow",
			"version": 1006,
			"versionNonce": 1265912394,
			"isDeleted": false,
			"id": "7LGdoFGWDF3Zo81VARaVz",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 404.06670085915476,
			"y": 871.971538344997,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 55.02238724407135,
			"height": 56.56383684972707,
			"seed": 944377750,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1700930556803,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "oWMeZUmSya4Ch50LeHMX0",
				"focus": 0.15859536150484885,
				"gap": 7.218495689021893
			},
			"endBinding": {
				"elementId": "bbu_er41_bjt708ACAd_W",
				"focus": 0.6286762264886586,
				"gap": 10.099874736381935
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-20.82279370354837,
					21.16871248540872
				],
				[
					-34.49487157224888,
					32.30244979598467
				],
				[
					-55.02238724407135,
					56.56383684972707
				]
			]
		},
		{
			"type": "text",
			"version": 1789,
			"versionNonce": 209966934,
			"isDeleted": false,
			"id": "ghj4JLNF",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -161.4059157330487,
			"y": 1268.290615901834,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 155.5998992919922,
			"height": 25,
			"seed": 1868806486,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "xFDOcbXrafp2wCXk1Ef7b",
					"type": "arrow"
				}
			],
			"updated": 1700930556803,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Usando o cache",
			"rawText": "Usando o cache",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Usando o cache",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "arrow",
			"version": 2012,
			"versionNonce": 1286947338,
			"isDeleted": false,
			"id": "xFDOcbXrafp2wCXk1Ef7b",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -142.8629099064878,
			"y": 1264.8260713758527,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 53.109708166003145,
			"height": 89.86824661105425,
			"seed": 1150164630,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1700930576849,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "ghj4JLNF",
				"focus": -0.6161943741665642,
				"gap": 3.4645445259811822
			},
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-18.269214626416897,
					-38.2057987143769
				],
				[
					-6.998442744293811,
					-73.36704849221883
				],
				[
					34.84049353958625,
					-89.86824661105425
				]
			]
		},
		{
			"type": "text",
			"version": 1846,
			"versionNonce": 1796844554,
			"isDeleted": false,
			"id": "fudLGOhL",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 970.4731180620875,
			"y": 1349.7084600982128,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 188.11985778808594,
			"height": 50,
			"seed": 1749667350,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "p4HvxIJasA58CQdvdES9t",
					"type": "arrow"
				}
			],
			"updated": 1700930631493,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "emitindo um notify\npara tocar um som",
			"rawText": "emitindo um notify\npara tocar um som",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "emitindo um notify\npara tocar um som",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "arrow",
			"version": 1509,
			"versionNonce": 534485706,
			"isDeleted": false,
			"id": "p4HvxIJasA58CQdvdES9t",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1066.9885843161321,
			"y": 1342.4297464562653,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 75.44287178119316,
			"height": 111.75514237332504,
			"seed": 156474198,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1700930631493,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "fudLGOhL",
				"focus": -0.08920839141888734,
				"gap": 7.278713641947434
			},
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					10.613142058684389,
					-29.402097830408138
				],
				[
					37.398124754212404,
					-73.21742615675612
				],
				[
					75.44287178119316,
					-111.75514237332504
				]
			]
		},
		{
			"type": "text",
			"version": 2085,
			"versionNonce": 699659478,
			"isDeleted": false,
			"id": "tHrF5NMR",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1220.2446868896873,
			"y": 1292.8771203987378,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 191.3198699951172,
			"height": 100,
			"seed": 1805313482,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1700930680305,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "emitindo um notify\nde fimd a animação\npara ser utilizado\nno character",
			"rawText": "emitindo um notify\nde fimd a animação\npara ser utilizado\nno character",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "emitindo um notify\nde fimd a animação\npara ser utilizado\nno character",
			"lineHeight": 1.25,
			"baseline": 93
		},
		{
			"type": "arrow",
			"version": 2304,
			"versionNonce": 415835530,
			"isDeleted": false,
			"id": "ZYlvhLFFmdV5Ux8sFice8",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1280.5366496188506,
			"y": 1296.4675372513561,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 128.57392186853417,
			"height": 89.41323787456349,
			"seed": 2005900426,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1700930801788,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "oZrY8f5G1lsVIIAXNkNkD",
				"focus": -0.11685292987845292,
				"gap": 26.041130675015893
			},
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					36.42493364737629,
					-48.94116440311541
				],
				[
					78.21294400161491,
					-74.36125230921675
				],
				[
					128.57392186853417,
					-89.41323787456349
				]
			]
		},
		{
			"type": "text",
			"version": 2239,
			"versionNonce": 2040486998,
			"isDeleted": false,
			"id": "wNs2S6I8",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1633.7828024791895,
			"y": 1315.418749964387,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 150.09986877441406,
			"height": 50,
			"seed": 1122341578,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "Nig8SgZFvASsmVUmpigmR",
					"type": "arrow"
				},
				{
					"id": "G2KJvQrMK0VYxElAGEjPq",
					"type": "arrow"
				}
			],
			"updated": 1700930784923,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "três animações\nna Montage",
			"rawText": "três animações\nna Montage",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "três animações\nna Montage",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "arrow",
			"version": 2512,
			"versionNonce": 1341168202,
			"isDeleted": false,
			"id": "Nig8SgZFvASsmVUmpigmR",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1623.1578934537192,
			"y": 1328.3689095992042,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 224.78107105762888,
			"height": 204.62961752149658,
			"seed": 335496854,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1700930766524,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "wNs2S6I8",
				"focus": -0.7808702545498115,
				"gap": 10.624909025470288
			},
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-83.09865738748704,
					-96.91543741131773
				],
				[
					-155.94677967194048,
					-160.05353130614117
				],
				[
					-224.78107105762888,
					-204.62961752149658
				]
			]
		},
		{
			"type": "arrow",
			"version": 2789,
			"versionNonce": 2009078806,
			"isDeleted": false,
			"id": "loSuO8r2v4j9XWTHAxG4x",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1707.8781935663528,
			"y": 1315.8807452379453,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 96.767645510992,
			"height": 178.17721235997942,
			"seed": 855405514,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1700930760407,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-13.053620684489033,
					-53.555577825554565
				],
				[
					-46.65243011504231,
					-126.35505450461596
				],
				[
					-96.767645510992,
					-178.17721235997942
				]
			]
		},
		{
			"type": "arrow",
			"version": 3255,
			"versionNonce": 910338390,
			"isDeleted": false,
			"id": "G2KJvQrMK0VYxElAGEjPq",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1748.066908138251,
			"y": 1306.6635280606768,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 151.40939829443028,
			"height": 190.85782621271733,
			"seed": 1595375382,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1700930791208,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "wNs2S6I8",
				"focus": 0.3179592898339085,
				"gap": 8.755221903710208
			},
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					30.422532740919223,
					-82.53977224737378
				],
				[
					83.17252485887343,
					-150.50858056887023
				],
				[
					151.40939829443028,
					-190.85782621271733
				]
			]
		},
		{
			"type": "arrow",
			"version": 3247,
			"versionNonce": 170375638,
			"isDeleted": false,
			"id": "-EH0RDo_5dDGQT34oYhWM",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -197.65417861311903,
			"y": 1688.5033051980513,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 112.81162511472996,
			"height": 68.73447951801222,
			"seed": 70306570,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1700930871172,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "Vl3un45g",
				"focus": 0.03559313605458169,
				"gap": 11.060358242786378
			},
			"endBinding": {
				"elementId": "OVSVM-hPvxYWVNWZ4Ear_",
				"focus": -0.4337637015490731,
				"gap": 11.373385492496396
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-16.491560107154896,
					-31.20862184760813
				],
				[
					-51.8093829653684,
					-58.16820676322118
				],
				[
					-112.81162511472996,
					-68.73447951801222
				]
			]
		},
		{
			"type": "text",
			"version": 2062,
			"versionNonce": 1041857546,
			"isDeleted": false,
			"id": "Vl3un45g",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -262.8871309080545,
			"y": 1699.5636634408377,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 186.4798583984375,
			"height": 100,
			"seed": 312205962,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "-EH0RDo_5dDGQT34oYhWM",
					"type": "arrow"
				}
			],
			"updated": 1700930881625,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "exemplo de um\nsolver para alinhar\nos pés no chão\nusando trace",
			"rawText": "exemplo de um\nsolver para alinhar\nos pés no chão\nusando trace",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "exemplo de um\nsolver para alinhar\nos pés no chão\nusando trace",
			"lineHeight": 1.25,
			"baseline": 93
		},
		{
			"type": "arrow",
			"version": 3929,
			"versionNonce": 103263638,
			"isDeleted": false,
			"id": "F9tIa-koAh7hCY0cgJJyE",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 70.19517695048765,
			"y": 1772.240596347529,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 329.40504375089904,
			"height": 219.77120494494034,
			"seed": 790448842,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1700930931348,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "d6wPdmIg",
				"focus": 0.4047597633643552,
				"gap": 8.683925633217854
			},
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-116.76632333969802,
					32.68156674465149
				],
				[
					-230.01190973618063,
					107.71575848924181
				],
				[
					-329.40504375089904,
					219.77120494494034
				]
			]
		},
		{
			"type": "text",
			"version": 2359,
			"versionNonce": 181334666,
			"isDeleted": false,
			"id": "d6wPdmIg",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 78.8791025837055,
			"y": 1708.5254006520202,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 289.0997314453125,
			"height": 125,
			"seed": 1199399306,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "F9tIa-koAh7hCY0cgJJyE",
					"type": "arrow"
				}
			],
			"updated": 1700930928212,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Control Rig sendo aplicado\ndepois das poses. No exemplo\né aplicado apenas quando\na velocidade do movimento\né maior que zero",
			"rawText": "Control Rig sendo aplicado\ndepois das poses. No exemplo\né aplicado apenas quando\na velocidade do movimento\né maior que zero",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Control Rig sendo aplicado\ndepois das poses. No exemplo\né aplicado apenas quando\na velocidade do movimento\né maior que zero",
			"lineHeight": 1.25,
			"baseline": 118
		},
		{
			"type": "arrow",
			"version": 3708,
			"versionNonce": 563675606,
			"isDeleted": false,
			"id": "az1RGfmfPxH1EBSB4Kr3A",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -789.7054361670121,
			"y": 2218.560175566241,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 207.09599975958804,
			"height": 77.70996096408044,
			"seed": 420377674,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1700930969748,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "lSDSGIkU",
				"focus": 0.00404829719853641,
				"gap": 11.060358242785696
			},
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-47.05248502132156,
					-51.60007390315286
				],
				[
					-107.00998991712629,
					-77.70996096408044
				],
				[
					-207.09599975958804,
					-68.73447951801245
				]
			]
		},
		{
			"type": "text",
			"version": 2259,
			"versionNonce": 1275554198,
			"isDeleted": false,
			"id": "lSDSGIkU",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -870.2056595116102,
			"y": 2229.6205338090267,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 248.27980041503906,
			"height": 75,
			"seed": 2089638666,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "az1RGfmfPxH1EBSB4Kr3A",
					"type": "arrow"
				}
			],
			"updated": 1700930960670,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "os bones da skeletal\nmesh do character foram\nimportados",
			"rawText": "os bones da skeletal\nmesh do character foram\nimportados",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "os bones da skeletal\nmesh do character foram\nimportados",
			"lineHeight": 1.25,
			"baseline": 68
		}
	],
	"appState": {
		"theme": "dark",
		"viewBackgroundColor": "#ffffff",
		"currentItemStrokeColor": "#9c36b5",
		"currentItemBackgroundColor": "transparent",
		"currentItemFillStyle": "solid",
		"currentItemStrokeWidth": 2,
		"currentItemStrokeStyle": "solid",
		"currentItemRoughness": 1,
		"currentItemOpacity": 100,
		"currentItemFontFamily": 1,
		"currentItemFontSize": 20,
		"currentItemTextAlign": "left",
		"currentItemStartArrowhead": null,
		"currentItemEndArrowhead": "arrow",
		"scrollX": 2232.404280479529,
		"scrollY": 932.0583963679251,
		"zoom": {
			"value": 0.441568610198796
		},
		"currentItemRoundness": "round",
		"gridSize": null,
		"gridColor": {
			"Bold": "#C9C9C9FF",
			"Regular": "#EDEDEDFF"
		},
		"currentStrokeOptions": null,
		"previousGridSize": null,
		"frameRendering": {
			"enabled": true,
			"clip": true,
			"name": true,
			"outline": true
		}
	},
	"files": {}
}
```
%%