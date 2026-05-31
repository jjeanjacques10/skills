# AI Skills Repository

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](./LICENSE)
![Status](https://img.shields.io/badge/status-active-success)
![Skills](https://img.shields.io/badge/skills-1-blue)
[![skills.sh](https://skills.sh/b/jjeanjacques10/skills)](https://skills.sh/jjeanjacques10/skills)

Repositório open source com skills reutilizáveis para agentes de IA, estruturado para instalação direta via `skills` CLI e descoberta no [skills.sh](https://www.skills.sh/).

## Visão geral

Este repositório organiza skills por categoria para facilitar descoberta, manutenção e compartilhamento entre agentes como Claude Code, Codex, Cursor, Copilot e outros compatíveis com o padrão `SKILL.md`.

O formato seguido aqui é o esperado pelo ecossistema `skills.sh`:

- cada skill vive em uma pasta própria
- cada skill possui `SKILL.md`
- `SKILL.md` começa com YAML frontmatter contendo ao menos `name` e `description`
- arquivos auxiliares podem ficar em `references/`, `templates/`, `scripts/` e `assets/`

## Instalação

Para listar as skills disponíveis neste repositório:

```bash
npx skills add jjeanjacques10/skills --list
```

Para instalar uma skill específica:

```bash
npx skills add jjeanjacques10/skills --skill spec-driven-build
```

Para instalar globalmente para seu agente:

```bash
npx skills add jjeanjacques10/skills --skill spec-driven-build -g -y
```

Também é possível instalar apontando para a URL completa do repositório:

```bash
npx skills add https://github.com/jjeanjacques10/skills --skill spec-driven-build
```

## Estrutura do repositório

```text
/skills
  /development
    /spec-driven-build
      SKILL.md
      /references
      /templates

/templates
  /skill-template
    SKILL.md
```

Cada skill segue este padrão:

```text
my-skill/
├── SKILL.md
├── references/
├── templates/
├── scripts/
└── assets/
```

## Skills disponíveis

| Skill | Categoria | Descrição curta |
|---|---|---|
| [`spec-driven-build`](./skills/development/spec-driven-build/SKILL.md) | development | Orquestra PRD, SPEC e tasks com gates de qualidade e histórico por feature. |

## Como usar sem CLI

Se preferir usar manualmente:

1. Clone o repositório.
2. Abra a skill desejada em `skills/`.
3. Leia o `SKILL.md`.
4. Carregue os arquivos em `references/` e `templates/` quando a própria skill pedir.

## Convenções

- nomenclatura em `kebab-case`
- frontmatter YAML obrigatório com `name` e `description`
- descrição pensada como gatilho de ativação da skill
- categorias oficiais: `development`, `design`, `productivity`, `others`
- template base em [`templates/skill-template/SKILL.md`](./templates/skill-template/SKILL.md)

## Contribuição

Consulte [CONTRIBUTING.md](./CONTRIBUTING.md) para o padrão de estrutura, frontmatter e checklist de publicação.

## Licença

Distribuído sob licença MIT. Veja [LICENSE](./LICENSE).
