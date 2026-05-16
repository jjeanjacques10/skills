# Contributing Guidelines

Obrigado por contribuir com o **AI Skills Repository**.

## 1) Estrutura obrigatória por skill

Toda skill deve seguir:

```text
<nome-da-skill>/
├── SKILL.md
├── scripts/      (opcional)
├── references/   (opcional)
├── assets/       (opcional)
└── ...           (opcional)
```

## 2) Nomenclatura

- Pasta da skill em **kebab-case**.
- Nome curto, descritivo e orientado ao resultado.
- Exemplos: `spec-driven-build`, `meeting-summary`, `ui-audit`.

## 3) Categorias

Adicione skills somente nas categorias oficiais:

- `skills/development/`
- `skills/design/`
- `skills/productivity/`
- `skills/others/`

## 4) Campos obrigatórios no SKILL.md

- Nome da skill
- Descrição
- Objetivo
- Categoria
- Tags
- Ferramentas compatíveis
- Como usar
- Prompt principal
- Exemplos de entrada
- Exemplos de saída
- Casos de uso
- Limitações
- Boas práticas

## 5) Tags padronizadas

- Minúsculas
- Sem acentuação
- Separadas por vírgula
- Ex.: `specification,planning,software-design,task-breakdown`

## 6) Idioma da skill

- O repositório aceita skills em **Português** ou **Inglês**.
- Cada `SKILL.md` deve manter **consistência interna** (não misturar idiomas nas seções principais).
- Se possível, priorize versão em Inglês para compartilhamento internacional.

## 7) Checklist de PR

- [ ] Estrutura da skill está no padrão do repositório.
- [ ] `SKILL.md` contém todos os campos obrigatórios.
- [ ] Categoria e tags seguem convenções.
- [ ] Idioma da skill está consistente (PT-BR ou EN).
- [ ] README atualizado (quando necessário).
