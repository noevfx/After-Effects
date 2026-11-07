# After Effects

Repositorio oficial de scripts, painéis, extensões e ferramentas de automação para Adobe After Effects.

## Projetos atuais

### Scripts & Extensões de Produção
- `AE Toolkit Panel/`: painel único de ScriptUI (encaixável ou janela flutuante) com um conjunto de 12 ferramentas de produção do dia a dia (Tidy, Reduce Project, Remove Unused Footage, Clear Expressions, Reset Layer, Hold Time Remap, Hold Keyframe, Copy/Paste Curve, Layer Normalize, Split Shapes, Precomp Extractor e Layer Organizer).
- `Layer Direction/`: script e extensão CEP para alinhamento e direção de camadas.
- `Swatch Colors/`: extensão CEP para extrair, salvar e aplicar paletas da composição ativa.
- `Text Splitter/`: script para dividir textos em letras, palavras ou linhas.
- `_Run Scripts/`: biblioteca de utilitários rápidos (Text Swap, Batch Comp, Faux 3D Extrusion, etc.).

### Automação & MCP Bridge
- `AE-mcp/`: servidor Model Context Protocol (MCP) e ponte CEP para controle em tempo real do After Effects via agentes de IA.
  - `ae-mcp-server/`: servidor Node.js MCP.
  - `cep-bridge/`: painel de comunicação CEP com o After Effects.
  - Pacote com instalador automatizado: `release/AE MCP/v1.0.0/` e `AE-mcp/release/v1.0.0/`.

## Releases

Cada produto tem a sua pasta de versões em `release/<Produto>/vX.Y.Z/` (ordem crescente, nada é sobrescrito). Versões atuais e histórico: [`CHANGELOG.md`](CHANGELOG.md). Como continuar o projeto: [`HANDOFF.md`](HANDOFF.md).

## Diretrizes de Desenvolvimento

Antes de alterar qualquer script, consulte `VERSIONING.md`.

Sempre siga o versionamento SemVer (`MAJOR.MINOR.PATCH`) e faça commits em português com prefixos semânticos padronizados.
