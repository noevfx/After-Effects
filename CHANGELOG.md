# Changelog — After Effects

Versionamento semântico (`MAJOR.MINOR.PATCH`) **por produto**. Cada versão publicada fica em `release/<Produto>/vX.Y.Z/` e nunca é sobrescrita. Diretriz completa: `D:\.IA agents\global\RELEASES.md`.

## Versões atuais

| Produto | Versão | Tipo | Pacote |
| :--- | :--- | :--- | :--- |
| AE Toolkit Panel | 1.0.5 | painel ScriptUI com 12 ferramentas | `release/AE Toolkit Panel/v1.0.5/` |
| Layer Direction | 1.0.0 | script + extensão CEP | `release/Layer Direction/v1.0.0/` |
| Swatch Colors | 1.0.3 | extensão CEP + ScriptUI | `release/Swatch Colors/v1.0.3/` |
| Text Splitter | 1.0.0 | script | `release/Text Splitter/v1.0.0/` |
| Precomp Extractor | 1.0.0 | script | `release/Precomp Extractor/v1.0.0/` |
| Text Swap | 1.1.0 | script (fica também em `_Run Scripts`) | `release/Text Swap/v1.1.0/` |
| AE MCP | 1.0.0 | servidor MCP + ponte CEP | `release/AE MCP/v1.0.0/` |

Fora desta tabela: `CompCAM/` (repositório próprio, `0.1.0`) e `AE-mcp/` (cópia antiga do MCP, repositório próprio).

---

## Repositório

### 2026-10-25 — Reorganização
- A pasta `Scripts AE` subiu um nível: a raiz de `After Effects\` passou a ser a raiz deste repositório. `CompCAM\` e `AE-mcp\` continuam dentro dela, cada um com seu `.git` (ignorados aqui).
- Releases passaram de `dist_releases/` (solto) para `release/<Produto>/vX.Y.Z/`, incluindo os zips antigos (`AE Toolkit Panel` 1.0.4, `Swatch Colors` CEP, `AE MCP`).
- `AE-MCP-Instalador-Completo.zip` era idêntico (mesmo hash) a `AE-MCP-Bridge-v1.0.0.zip`: ficou uma cópia só.
- `_Run Scripts` unificado com `Documents\_Run Scripts`: 37 arquivos. Os 4 que são de terceiros ou pessoais (`ParentAlign_v4.jsx`, `Scale Composition.jsx`, `Scale Selected Layers.jsx`, `_EasyCurveClipboard.txt`) ficam só locais (no `.gitignore`).

---

## AE Toolkit Panel
- **1.0.5** (2026-09-18) — *Reset Layer* volta a âncora para o centro da canvas nativa.
- **1.0.4** (2026-08-30) — *Split Shapes* reconhece Live Text de PSD; *Layer Normalize* ganha diagnóstico e lida com o limite de `fontSize`.
- **1.0.3** (2026-08-30) — diagnóstico no alerta final do *Tidy*.
- **1.0.2** (2026-08-28) — "Reorganize entire project" vem marcado por padrão.
- **1.0.1** (2026-08-28) — *Tidy* reaudita pastas próprias e ganha reorganização total opcional.
- **1.0.0** (2026-08-28) — painel único que substitui o Declutter e scripts avulsos: Tidy, Reduce Project, Remove Unused Footage, Clear Expressions, Reset Layer, Hold Time Remap, Hold Keyframe, Copy/Paste Curve, Layer Normalize, Split Shapes, Precomp Extractor e Layer Organizer.

## Swatch Colors
- **1.0.3** (2026-08-20) — corrige a cópia do HEX para a área de transferência; reconhece cores chapadas do frame como cores exatas.
- **1.0.2** (2026-08-20) — CEP e ScriptUI sincronizados na mesma versão; versão ScriptUI com instalador; recurso *ADD COLOR* (color picker do AE) restaurado.
- **1.0.1** (2026-08-18) — instalação corrigida.
- **1.0.0** (2026-08-16) — primeira versão (extensão CEP).

## Layer Direction
- **1.0.0** (2026-08-14) — primeira versão: script e extensão CEP de alinhamento e direção de camadas, com manual do usuário (PDF).

## Text Splitter
- **1.0.0** (2026-08-14) — primeira versão: divide textos em letras, palavras ou linhas.

## Precomp Extractor
- **1.0.0** (2026-08-20) — extrai pré-composições preservando transformações (também é uma das ferramentas do AE Toolkit Panel).

## Text Swap
- **1.1.0** (2026-09-23) — cadeia de N layers, estilo e cor por caractere, corte seco e surgimento.
- **0.2.0** (2026-09-18) — rig de troca de estilo por caractere, palavra ou linha.
- **0.1.0** (2026-09-18) — estrutura inicial.

## AE MCP
- **1.0.0** — servidor MCP (Node.js) + ponte CEP que substituiu o polling por `scheduleTask`, com instalador completo para Windows novo (2026-08-01 a 2026-08-16). Unificado neste repositório em 2026-10-20 (`mcp/`).

## _Run Scripts (scripts isolados, de comando único, sem interface)
Versões internas conhecidas: Faux 3D Extrusion Rig `4.8.1`, Texto 3D `2.0.0` (v02; a v01 é anterior), Easy Physics `1.0.0`, Layer Organizer `1.1.0`, Limpar FX/Expressões `2.0.0`, Text Swap `1.1.0`. Os demais não declaram versão e valem como `1.0.0`.
