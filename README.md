# AI Skills Repository

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](./LICENSE)
![Status](https://img.shields.io/badge/status-active-success)
![Skills](https://img.shields.io/badge/skills-2-blue)
![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)

Repositório open source para centralizar, reutilizar e compartilhar SKILLs/prompts estruturados para múltiplos agentes e ferramentas de IA.

---

## 📚 Table of Contents

- [Visão geral](#-visão-geral)
- [Estrutura do repositório](#-estrutura-do-repositório)
- [Skills disponíveis](#-skills-disponíveis)
- [Como usar](#-como-usar)
  - [Claude Code](#claude-code)
  - [Cursor](#cursor)
  - [ChatGPT](#chatgpt)
  - [Devin](#devin)
- [Convenções](#-convenções)
- [Placeholders visuais](#-placeholders-visuais)
- [Contribuição](#-contribuição)
- [Licença](#-licença)

---

## 🚀 Visão geral

Este projeto organiza SKILLs por categoria para facilitar descoberta, manutenção e expansão contínua.

Ferramentas alvo:
- Claude
- Claude Code
- Devin
- Cursor
- ChatGPT
- Windsurf
- Copilot
- Outras ferramentas compatíveis com prompts estruturados

---

## 🗂 Estrutura do repositório

```text
/skills
  /development
    /code-review
    /architecture
    /debugging
    /refactoring
    /spec-driven-build

  /design
    /ui-ux
    /branding
    /landing-pages

  /productivity
    /documentation
    /meeting-summary
    /planning

  /others
```

Cada skill segue o padrão:

```text
my-skill/
├── SKILL.md          # obrigatório
├── scripts/          # opcional
├── references/       # opcional
├── assets/           # opcional
└── ...               # extensível
```

---

## 🧩 Skills disponíveis

| Skill | Categoria | Compatibilidade | Descrição curta |
|---|---|---|---|
| [`spec-driven-build`](./skills/development/spec-driven-build/SKILL.md) | development | Claude, Claude Code, ChatGPT, Cursor, Devin, Copilot | Gera SDD detalhado e tasks granulares para correções/features. |
| [`meeting-summary`](./skills/productivity/meeting-summary/SKILL.md) | productivity | Claude, Claude Code, ChatGPT, Cursor, Devin, Copilot | Estrutura notas de reunião em resumo com decisões e ações. |

---

## 🛠 Como usar

### Passo a passo geral

1. Clone o repositório.
2. Escolha uma skill na pasta `skills/`.
3. Abra o arquivo `SKILL.md`.
4. Copie o prompt/instruções.
5. Use na ferramenta desejada.
6. Customize para seu contexto.

### Claude Code

```bash
git clone https://github.com/jjeanjacques10/skills.git
cd skills
# Abra: skills/development/spec-driven-build/SKILL.md
```

Depois, copie o conteúdo de **Prompt principal** para o Claude Code.

### Cursor

- Abra o repositório no Cursor.
- Selecione uma skill e copie o prompt principal.
- Cole no chat do agente e adapte ao ticket/issue.

### ChatGPT

- Abra a skill desejada (`SKILL.md`).
- Copie o prompt principal e contexto.
- Execute no ChatGPT com os dados do seu projeto.

### Devin

- Defina a tarefa no Devin.
- Inclua o prompt da skill como instrução base.
- Anexe arquivos/requisitos adicionais do projeto.

---

## 🧭 Convenções

- **Nomenclatura**: `kebab-case` (ex.: `spec-driven-build`).
- **Tags padronizadas**: usar minúsculas, sem acentos, separadas por vírgula.
- **Categorias oficiais**: `development`, `design`, `productivity`, `others`.
- **Template**: use [`templates/skill-template/`](./templates/skill-template/) para novas skills.

---

## 🖼 Placeholders visuais

> As imagens/screenshot serão adicionadas depois.

- `docs/images/placeholder-overview.png` *(placeholder)*
- `docs/images/placeholder-skill-card.png` *(placeholder)*

---

## 🤝 Contribuição

Consulte [CONTRIBUTING.md](./CONTRIBUTING.md) para padrão de nomenclatura, estrutura obrigatória e checklist de submissão.

---

## 📄 Licença

Distribuído sob licença MIT. Veja [LICENSE](./LICENSE).
