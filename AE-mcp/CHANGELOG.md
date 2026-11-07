# Changelog — AE-mcp

Versionamento semântico. Cada versão fica em `release/vX.Y.Z/` e não é sobrescrita (diretriz: `D:\.IA agents\global\RELEASES.md`).

## [1.0.0] — 2026-08-16

Pacotes: `release/v1.0.0/AE-MCP-Instalador-Completo-v1.0.0.zip` e `release/v1.0.0/AE-MCP-CEP-Bridge-v1.0.0.zip`.

- **2026-08-16** — instalador completo para Windows novo (zip com instalador automatizado).
- **2026-08-16** — ponte CEP (`com.aemcp.bridge`) no lugar do polling por `app.scheduleTask`: acabou o erro "Cannot run a script while a modal dialog is waiting for response". O contrato `task.json`/`result.json` não mudou.
- **2026-08-01** — primeiro commit: servidor MCP de automação do After Effects (Node.js/TypeScript) com 16 ferramentas e integração com o Antigravity.

## Não lançado (alterações locais sem commit em 2026-10-25)
- `ae-mcp-server/dist/ae-runner.js`, `cep-bridge/jsx/host.jsx` e `cep-bridge/README.md` têm modificações ainda não commitadas. Revisar e, se forem para valer, lançar como `1.0.1`. O `AE-MCP-Instalador-Completo-v1.0.0.zip` da pasta `release` é a versão local (já com essas alterações), diferente da que foi commitada em 2026-08-16.

## Repositório

### 2026-10-25 — Reorganização
- Os dois zips que ficavam na raiz foram para `release/v1.0.0/` (com o número da versão no nome); criados `README.md`, `CHANGELOG.md`, `HANDOFF.md` e `version.txt`.
- A pasta mudou de `D:\_Claude\AE-mcp` para `D:\Noe VFX\.Labs\After Effects\AE-mcp`; os clientes MCP (Claude Code e Codex) foram atualizados para o novo caminho.
