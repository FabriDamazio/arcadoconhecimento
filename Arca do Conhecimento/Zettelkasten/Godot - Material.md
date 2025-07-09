---
Criado: 2025-06-14T12:38
Atualizado: 2025-06-14T12:38
Estudado: 2025-07-09T10:33
Links:
  - "[[Godot Engine]]"
  - "[[Texturas em jogos 3D]]"
  - "[[UV Mapping]]"
  - "[[Mesh em desenvolvimento de jogos 3D]]"
  - "[[Renderização Baseada em Física (Physically Based Rendering - PBR)]]"
---
---
# Godot - Material

Na Godot Engine 4, um Material é um recurso que define como a superfície de uma Mesh ou outro objeto visual será renderizada. Ele controla como a luz interage com o objeto, quais texturas são usadas e quais efeitos visuais são aplicados.

O Material funciona como uma camada intermediária entre a Mesh e a renderização final, utilizando as informações de Texturas, Shaders e Parâmetros visuais.

A Godot 4 implementa [[Renderização Baseada em Física (Physically Based Rendering - PBR)]] através do node `StandardMaterial3D`, utilizando o [[Metal-Roughness Workflow]] por padrão.

## Tipos de Material na Godot 4

- **StandardMaterial3D**: Material padrão para objetos 3D. Oferece controles para cor, texturas, reflexão, transparência, emissividade, etc.
- **ShaderMaterial**: Permite personalizar completamente o comportamento visual usando shaders escritos pelo usuário, usando a linguagem de shaders da Godot.
- **ParticleProcessMaterial**: Material específico para sistemas de partículas.

## Principais Propriedades do StandardMaterial3D

- Albedo (Color / Texture): Define a cor base e a textura de cor.
- Normal Map: Simula detalhes e relevo sem adicionar geometria.
- Roughness / Metallic: Controla como a superfície reflete a luz.
- Emission: Faz o objeto emitir luz (brilho próprio).
- Transparency / Alpha: Permite superfícies translúcidas ou transparentes.
- Cull Mode: Determina se as faces traseiras da Mesh são renderizadas ou não.

## Fluxo Básico de Uso

- Criar uma Mesh (ex.: MeshInstance3D).
-  Criar e configurar um Material (ex.: StandardMaterial3D).
- Atribuir o Material à Mesh.
- Adicionar Texturas ao Material (ex.: Albedo, Normal, etc.).
- Ajustar propriedades como brilho, transparência, emissividade, etc.

---
## References

GODOT ENGINE. **Material — Godot Engine (stable documentation)**. Disponível em: [https://docs.godotengine.org/en/stable/classes/class_material.html](https://docs.godotengine.org/en/stable/classes/class_material.html). Acesso em: 14 jun. 2025.