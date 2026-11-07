# After Effects — HANDOFF

Raiz do repositório `noevfx/After-Effects` (git próprio). Scripts, painéis, extensões e o MCP de After Effects do ecossistema Noé VFX. Regras gerais: `D:\.IA agents\global\AGENTS.md` e `RELEASES.md`.

## Mapa

```text
After Effects\
├─ AE Toolkit Panel\   painel ScriptUI (12 ferramentas) + instalador .bat
├─ Layer Direction\    script, extensão CEP e manual (PDF)
├─ Swatch Colors\      extensão CEP + versão ScriptUI (versões sempre iguais)
├─ Text Splitter\      script
├─ _Run Scripts\       scripts isolados de comando único, sem interface (espelho em Documents\_Run Scripts)
├─ Tools\              utilitários de manutenção (setup-links.ps1, clipboard-diagnostic.jsx)
├─ release\<Produto>\vX.Y.Z\   pacotes de cada versão, em ordem crescente
├─ CompCAM\            repositório próprio (câmera virtual, 0.1.0) — não faz parte deste repo
└─ AE-mcp\             MCP oficial do After Effects (vai dentro do repositório `noevfx/After-Effects`; hoje tem `.git` próprio, que sai no primeiro envio: servidor Node, painel CEP e skill)
```

## Regras do código

- ExtendScript **ES3 estrito**: sem `let`, `const`, arrow functions, `map`, `forEach`, `JSON` nativo.
- Padrões do After Effects: `D:\.IA agents\manuais\AE_PATTERNS.md`.
- Versão de cada produto fica no cabeçalho do script ou no manifest da extensão; `Swatch Colors` mantém CEP e ScriptUI na mesma versão.
- Commits em português (`feat:`, `fix:`, `docs:`, `chore:`, `release:`).

## Instalar para testar

- Painéis ScriptUI vão para `C:\Program Files\Adobe\Adobe After Effects 2026\Support Files\Scripts\ScriptUI Panels` (copiar exige administrador: `Start-Process -Verb RunAs`).
- Extensões CEP vão para `%APPDATA%\Adobe\CEP\extensions` (a cópia instalada é independente da fonte: depois de editar a fonte, copiar de novo).
- `_Run Scripts` roda de `C:\Users\enn_g\Documents\_Run Scripts`; ao editar um script, copiar para os dois lugares.

## Como lançar uma versão

Seguir `D:\.IA agents\global\RELEASES.md`. Em resumo, por produto: backup em `_backups\` → atualizar a versão e o `CHANGELOG.md` → gerar o zip em `release\<Produto>\vX.Y.Z\` → commit → publicar e espelhar no Drive. Release publicada é imutável.

## Estado e pendências (2026-10-25)

- Reorganizado em 2026-10-25 (ver `CHANGELOG.md`). Ainda nada foi enviado ao GitHub: os repositórios `noevfx/...` serão criados e enviados só com ordem do Eduardo ("pode subir pro git").
- **MCP oficial = `AE-mcp\`** (decidido em 26/10/2026: é o que os clientes usam, tem edições até 23/10 e o painel instalado é idêntico). A cópia `mcp\` que estava no repositório foi para `_Arquivo\After Effects\mcp-copia-no-repo`; no git ela aparecerá como removida.
- `AE-mcp\` tem alterações sem commit (`dist/ae-runner.js`, `cep-bridge/jsx/host.jsx`, `cep-bridge/README.md`).
- `_Run Scripts`: **Texto 3D v01 e v02 são formas alternativas e complementares (não apagar nenhuma)**, confirmado pelo usuário em 26/10/2026. Pendente só decidir a família `Organic_Waveform*` (4 variações); manter até haver ok.
- Não existe README próprio nas pastas `Layer Direction`, `Text Splitter` e `AE Toolkit Panel`; a descrição deles está no README da raiz.
