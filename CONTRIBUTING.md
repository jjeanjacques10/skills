# Contributing Guidelines

Obrigado por contribuir com o **AI Skills Repository**.

## 1) Estrutura obrigatória por skill

Toda skill publicada neste repositório deve seguir:

```text
<nome-da-skill>/
├── SKILL.md
├── references/   (opcional)
├── templates/    (opcional)
├── scripts/      (opcional)
├── assets/       (opcional)
└── ...           (opcional)
```

## 2) Compatibilidade com `skills.sh`

O repositório é mantido para funcionar com o `skills` CLI e aparecer corretamente no `skills.sh`.

Por isso, cada `SKILL.md` deve:

- começar com YAML frontmatter válido
- declarar `name`
- declarar `description`
- usar uma `description` que ajude o agente a decidir quando ativar a skill

Exemplo mínimo:

```yaml
---
name: my-skill
description: Do X for Y projects. Use when the user asks about X or mentions Y.
---
```

## 3) Nomenclatura

- Pasta da skill em `kebab-case`
- Nome curto, descritivo e orientado ao resultado
- Exemplos: `spec-driven-build`, `meeting-summary`, `ui-audit`

## 4) Corpo recomendado do `SKILL.md`

O corpo em Markdown é livre, mas recomendamos esta estrutura:

- o que a skill faz
- quando usar e quando nao usar
- entradas necessarias
- procedimento passo a passo
- validacao ou definicao de pronto
- falhas comuns e como corrigir

## 5) Categorias

Adicione skills somente nas categorias oficiais:

- `skills/development/`
- `skills/design/`
- `skills/productivity/`
- `skills/others/`

## 6) Idioma da skill

- O repositório aceita skills em Português ou Inglês
- Cada `SKILL.md` deve manter consistência interna
- Se a skill for pública e ampla, prefira Inglês ou uma descrição claramente compreensível internacionalmente

## 7) Checklist de PR

- [ ] A skill segue a estrutura de pastas do repositório
- [ ] O `SKILL.md` contém frontmatter YAML válido
- [ ] O frontmatter possui `name` e `description`
- [ ] A descrição funciona como gatilho de ativação
- [ ] Links para `references/`, `templates/`, `scripts/` e `assets/` estão corretos
- [ ] README atualizado quando necessário
