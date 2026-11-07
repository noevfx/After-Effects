# After Effects — ferramentas da Noé VFX

Scripts, painéis e uma ponte de IA para o **Adobe After Effects**, feitos no dia a dia de produção de vídeo e motion. Tudo aqui é gratuito, sem dependências obscuras, e cada ferramenta tem o seu pacote pronto para instalar.

> **Não sabe por onde começar?** Instale o **AE Toolkit Panel**: é um painel único com 12 ferramentas de limpeza e organização de projeto. As outras são extras que você instala quando precisar.

## O que tem aqui

| Ferramenta | Para que serve | Versão | Baixar |
| :--- | :--- | :--- | :--- |
| **AE Toolkit Panel** | Painel com 12 ferramentas: organizar projeto, remover footage sem uso, limpar expressões, Time Remap, copiar/colar curvas, dividir shapes e mais | 1.0.5 | [zip](release/AE%20Toolkit%20Panel/v1.0.5/AE-Toolkit-Panel-v1.0.5.zip) |
| **Layer Direction** | Alinha e dá direção às camadas (rotação apontando para onde o objeto vai) | 1.0.0 | [zip](release/Layer%20Direction/v1.0.0/Layer-Direction-v1.0.0.zip) |
| **Swatch Colors** | Extrai, salva e aplica paletas de cores da composição ativa | 1.0.3 | [zip](release/Swatch%20Colors/v1.0.3/Swatch-Colors-v1.0.3.zip) |
| **Text Splitter** | Divide um texto em letras, palavras ou linhas (uma camada para cada) | 1.0.0 | [zip](release/Text%20Splitter/v1.0.0/Text-Splitter-v1.0.0.zip) |
| **Text Swap** | Troca o texto de várias camadas de uma vez | 1.1.0 | [zip](release/Text%20Swap/v1.1.0/Text-Swap-v1.1.0.zip) |
| **Precomp Extractor** | Extrai o conteúdo de pré-composições | 1.0.0 | [zip](release/Precomp%20Extractor/v1.0.0/Precomp-Extractor-v1.0.0.zip) |
| **AE MCP** (ponte de IA) | Deixa assistentes de IA (Claude, Codex) controlarem o After Effects | 1.0.0 | [zip](release/AE%20MCP/v1.0.0/AE-MCP-Bridge-v1.0.0.zip) |
| **_Run Scripts** | Biblioteca de utilitários rápidos de um clique (Batch Comp, Faux 3D Extrusion, Hold Time Remap…) | — | pasta [`_Run Scripts`](%5FRun%20Scripts) |

## Como instalar (painéis e scripts)

1. Baixe o `.zip` da ferramenta na tabela acima e extraia.
2. Rode o instalador que vem dentro (`Install_….bat` no Windows). Se a ferramenta vier só com um arquivo `.jsx`, copie-o para a pasta de scripts do After Effects, em `Support Files/Scripts/ScriptUI Panels`.
3. Abra o After Effects e vá em **Janela** (painéis) ou **Arquivo → Scripts** (scripts avulsos).

Se o script pedir, ative **Editar → Preferências → Scripting e Expressões → Permitir que scripts gravem arquivos e acessem a rede**.

## Ponte de IA (AE MCP)

O **AE MCP** usa o *Model Context Protocol*, um padrão que permite a um assistente de IA chamar ferramentas. Ele tem duas partes que conversam entre si:

```
Assistente de IA ─▶ servidor MCP (Node.js) ─▶ painel CEP dentro do After Effects ─▶ ExtendScript
```

O instalador do pacote (`AE-MCP-Instalador`) configura tudo. O código está em [`AE-mcp/`](AE-mcp), com o seu próprio [README](AE-mcp/README.md). **O painel precisa estar aberto dentro do After Effects** para a IA conseguir agir.

## Estrutura do repositório

```text
After Effects/
├─ AE Toolkit Panel/ Layer Direction/ Swatch Colors/ Text Splitter/   código de cada ferramenta
├─ _Run Scripts/                utilitários de um clique
├─ AE-mcp/                      servidor MCP e painel CEP da ponte de IA
├─ release/<Ferramenta>/vX.Y.Z/ pacote de cada versão (ordem crescente, nada é sobrescrito)
├─ CHANGELOG.md                 histórico de versões
└─ HANDOFF.md  VERSIONING.md    como continuar o projeto e regra de versões
```

O **CompCAM** (câmera virtual com o celular) é um projeto à parte e não faz parte deste repositório.

## Versões

Seguimos o versionamento `MAJOR.MINOR.PATCH`. O histórico completo está no [CHANGELOG](CHANGELOG.md); a regra, em [VERSIONING.md](VERSIONING.md).

## Contato

Noé VFX — [noevfx.com](https://noevfx.com) · [labs@noevfx.com](mailto:labs@noevfx.com)

Adobe e After Effects são marcas da Adobe. Estas ferramentas são independentes e não são afiliadas nem endossadas pela Adobe.
