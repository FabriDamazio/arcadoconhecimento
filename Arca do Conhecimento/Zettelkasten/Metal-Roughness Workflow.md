---
Criado: 2025-06-14T15:10
Atualizado: 2025-06-14T15:10
Estudado: 2025-07-30T17:12
Links:
  - "[[Godot - Material]]"
  - "[[Renderização Baseada em Física (Physically Based Rendering - PBR)]]"
tags:
  - gamedev
---
---
# Metal-Roughness Workflow

O **Metallic Workflow**, também chamado de **Metal-Roughness Workflow**, é um dos dois principais métodos de configuração de materiais dentro do modelo [[Renderização Baseada em Física (Physically Based Rendering - PBR)]], sendo o **padrão usado na Godot Engine 4**.

Esse workflow define como a luz interage com uma superfície 3D, controlando reflexos, brilho e aparência geral do material.

## Principais Parâmetros do Metallic Workflow

| **Albedo / Base Color** | Define a cor base da superfície (difusa ou refletiva).                             |
| ----------------------- | ---------------------------------------------------------------------------------- |
| **Metallic**            | Controla se o material se comporta como **metal** (valor entre 0 e 1).             |
| **Roughness**           | Define a aspereza da superfície, controlando a dispersão dos reflexos.             |
| **Specular Scalar**     | Um fator numérico para ajustar a intensidade geral do specular (usado na Godot 4). |
## Funcionamento do parâmetro Metallic

- **Metallic = 1** → Material é tratado como um **metal**: A cor de reflexo vem do **Albedo**, e a superfície não tem quase cor difusa.
- **Metallic = 0** → Material é tratado como **não-metálico (dielétrico)**: Reflexos são neutros (geralmente brancos) e a cor difusa vem diretamente do Albedo.
- **Valores intermediários (ex.: 0.5)** são raramente usados na prática.    

---

## Funcionamento do parâmetro Roughness

- **Roughness = 0.0** → Reflexos nítidos e brilhantes.
- **Roughness = 1.0** → Reflexos difusos, quase sem brilho.    

---

## Vantagens do Metallic Workflow

- **Simplicidade:** Menos mapas de texturas comparado ao Specular Workflow.
- **Compatibilidade:** Suportado nativamente em engines modernas (Godot, Unreal, Unity).
- **Eficiência:** Melhor desempenho em tempo real.
---
## References

WIKIPÉDIA. **Physically based rendering**. Disponível em: [https://en.wikipedia.org/wiki/Physically_based_rendering](https://en.wikipedia.org/wiki/Physically_based_rendering). Acesso em: 14 jun. 2025.

GODOT ENGINE. **StandardMaterial3D — Godot Engine (stable documentation)**. Disponível em: https://docs.godotengine.org/en/stable/classes/class_standardmaterial3d.html. Acesso em: 14 jun. 2025.