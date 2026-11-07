# AE-mcp — HANDOFF

Vai dentro do repositório `noevfx/After-Effects` (pasta `AE-mcp`); hoje tem `.git` próprio (3 commits), que sai no primeiro envio. Servidor MCP + ponte CEP do After Effects. Regras gerais: `D:\.IA agents\global\AGENTS.md`, `AE_PATTERNS.md` e `RELEASES.md`.

## Mapa

```text
AE-mcp\
├─ ae-mcp-server\   servidor MCP (src\ em TypeScript, dist\ compilado, setup.ps1, test_ae.ps1)
├─ cep-bridge\      painel CEP com.aemcp.bridge (js\main.js faz o polling; jsx\host.jsx executa no AE)
├─ .agents\         AGENTS.md e skill after_effects_controller
├─ backups\         cópias de ae-bridge.jsx (histórico do polling antigo)
├─ release\v1.0.0\  AE-MCP-Instalador-Completo-v1.0.0.zip, AE-MCP-CEP-Bridge-v1.0.0.zip
└─ version.txt  README.md  CHANGELOG.md  HANDOFF.md
```

## Build e teste

- `cd ae-mcp-server && npm install && npm run build` gera `dist\index.js` (é o que os clientes MCP executam).
- `ae-mcp-server\test_ae.ps1` testa a conversa com o After Effects (precisa do AE aberto e do painel CEP ativo).
- Cliente MCP (Claude Code e Codex): `node "D:\Noe VFX\.Labs\After Effects\AE-mcp\ae-mcp-server\dist\index.js"`. Depois de mover a pasta é preciso **reiniciar a sessão** do Claude Code/Codex para o servidor reconectar.
- A cópia instalada da ponte fica em `%APPDATA%\Adobe\CEP\extensions\com.aemcp.bridge` e é independente da fonte: depois de editar `cep-bridge\`, copiar de novo.

## Como lançar uma versão

`D:\.IA agents\global\RELEASES.md`: backup em `_backups\` → bump (`version.txt`, `ae-mcp-server\package.json`) e `CHANGELOG.md` → zips em `release\vX.Y.Z\` → commit → publicar e espelhar no Drive.

## Pendências (2026-10-25)

- **Duplicidade:** `..\mcp\` (repositório After-Effects) tem o mesmo conteúdo. Decidir qual é o oficial e arquivar o outro (a decisão também define para onde apontam Claude Code e Codex).
- **Alterações sem commit:** `ae-mcp-server/dist/ae-runner.js`, `cep-bridge/jsx/host.jsx`, `cep-bridge/README.md`; arquivos de teste soltos `ae-mcp-server/test-err.txt` e `test-out.txt`.
- Ainda nada foi enviado ao GitHub: os repositórios `noevfx/...` serão criados e enviados só com ordem do Eduardo ("pode subir pro git").
