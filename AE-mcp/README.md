# AE-mcp — MCP do After Effects

Controle o Adobe After Effects por agentes de IA (Claude Code, Codex, Antigravity) via **Model Context Protocol**. Versão **1.0.0**.

> **Atenção:** esta pasta é a cópia **independente e mais antiga** do MCP. O conteúdo é o mesmo de `..\mcp\` (repositório After-Effects, onde o MCP foi unificado em 2026-10-20). Hoje o Claude Code e o Codex apontam para **esta** pasta (`ae-mcp-server\dist\index.js`). Ver "Pendências" no [`HANDOFF.md`](HANDOFF.md).

## Como funciona

```
Agente de IA ──▶ ae-mcp-server (Node.js, 16 ferramentas) ──▶ task.json ──▶ painel CEP (com.aemcp.bridge) ──▶ ExtendScript (After Effects)
                                                          ◀── result.json ◀──
```

- `ae-mcp-server\`: servidor MCP em Node.js/TypeScript (`src\`, `dist\`). Ferramentas: `ae_get_project_elements`, `ae_create_composition`, `ae_create_text_layer`, `ae_create_solid_layer`, `ae_find_composition`, `ae_rename_composition`, `ae_batch_rename_compositions`, `ae_update_composition_settings`, `ae_update_text_layer`, `ae_animate_position`, `ae_apply_fill_effect`, `ae_change_font`, `ae_replace_footage`, `ae_replace_layer_source`, `ae_render_composition`, `ae_run_custom_script`.
- `cep-bridge\`: painel CEP que faz o polling de `task.json` fora do motor ExtendScript. Substituiu o `ae-bridge.jsx` com `app.scheduleTask`, que disparava o erro "Cannot run a script while a modal dialog is waiting". Detalhes em `cep-bridge\README.md`.
- `.agents\`: regras e skill `after_effects_controller` para o agente.

## Instalação

1. Pacote completo para uma máquina nova: `release\v1.0.0\AE-MCP-Instalador-Completo-v1.0.0.zip` (instalador automatizado).
2. Só a ponte CEP: `release\v1.0.0\AE-MCP-CEP-Bridge-v1.0.0.zip`.
3. Manual: copiar `cep-bridge\*` para `%APPDATA%\Adobe\CEP\extensions\com.aemcp.bridge`, rodar `npm install` e `npm run build` em `ae-mcp-server\` e registrar o servidor no cliente MCP:

```json
{ "after-effects": { "command": "node", "args": ["D:\\Noe VFX\\.Labs\\After Effects\\AE-mcp\\ae-mcp-server\\dist\\index.js"] } }
```

## Versões e releases

Cada versão fica em `release\vX.Y.Z\` e não é sobrescrita. Histórico em [`CHANGELOG.md`](CHANGELOG.md); como continuar em [`HANDOFF.md`](HANDOFF.md); diretriz em `D:\.IA agents\global\RELEASES.md`.
