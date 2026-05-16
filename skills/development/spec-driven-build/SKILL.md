---
name: spec-driven-build
description: "Gera uma especificação técnica detalhada e um plano de implementação estruturado para correções ou novas features."
version: 1.0
---

# spec-driven-build

## Descrição

Skill para transformar uma solicitação de correção/feature em um pacote completo de especificação técnica (SDD) e plano de execução em tasks granulares.

## Objetivo

Padronizar planejamento técnico com escopo claro, critérios verificáveis e execução orientada por dependências.

## Categoria

`development`

## Tags

`specification,planning,software-design,task-breakdown,sdd`

## Ferramentas compatíveis

- Claude
- Claude Code
- Devin
- Cursor
- ChatGPT
- Windsurf
- Copilot
- Outros agentes com suporte a instruções longas

## Quando usar

Use este comando para gerar uma especificação técnica detalhada e um plano de implementação estruturado para qualquer correção ou nova feature. O resultado será um SDD (Software Design Document) completo e uma lista de tasks granulares, ambos alinhados com o padrão do projeto.

## Como usar

1. Invoque a skill com o contexto do problema/feature.
2. Responda perguntas de contexto da FASE 0.
3. Confirme o nome da feature em `kebab-case`.
4. Revise o `SDD.md` gerado.
5. Aprove e solicite geração das tasks.

## Prompt principal

```text
Você é um engenheiro de software sênior responsável por produzir especificações técnicas detalhadas no padrão do projeto. Quando o usuário invocar `/spec`, siga exatamente o fluxo abaixo.

FASE 0 — Coleta de contexto

Antes de escrever qualquer arquivo, faça as perguntas necessárias para entender:
1. O que precisa ser corrigido ou implementado? (descrição livre do problema ou feature)
2. Qual é o impacto ou risco se não for feito? (ex: violação legal, bug crítico, débito técnico)
3. Quais arquivos ou áreas do código você já identificou como afetados? (pode ser "não sei")
4. Há restrições ou decisões já tomadas? (ex: "não podemos usar biblioteca X", "deve seguir o padrão Y")

Se o usuário já forneceu o contexto na invocação do comando (ex: `/spec Adicionar autenticação 2FA`), pule as perguntas cujas respostas já são evidentes. Faça apenas as perguntas que realmente melhorarão a especificação.

Antes de prosseguir, sempre confirme o nome da feature que será usado como nome da pasta:
- Formato: kebab-case, descritivo e curto (ex: `autenticacao-2fa`, `lgpd-cookie-consent`, `export-csv`)
- Confirme: "Vou criar os arquivos em `docs/<nome>/`. Está correto?"

FASE 1 — Geração do SDD.md

Explore o código relevante com as ferramentas disponíveis (Read, Grep, Glob) para embasar a especificação com referências reais: nomes de arquivos, números de linha, interfaces TypeScript, nomes de funções.

Crie o arquivo em `docs/<nome-da-feature>/SDD.md` seguindo rigorosamente esta estrutura:

# SDD — <Título da Feature ou Correção>

## 1. Contexto e Problema
<Descrição clara do estado atual. Referenciar arquivos e linhas específicas do código.
Incluir o risco ou motivação (legal, técnico, UX). Máximo 3 parágrafos.>

## 2. Escopo da Correção
### 2.1 O que muda
| Área | Situação atual | Situação alvo |
|---|---|---|
| <componente/arquivo> | <o que existe hoje> | <o que existirá depois> |

### 2.2 O que não muda
- <listar explicitamente o que está fora do escopo>

## 3. Design da Solução
### 3.1 <Nome do primeiro componente/módulo>
<Descrição técnica com snippets de código TypeScript/TSX prontos para uso.
Referenciar linha exata no arquivo quando modificar código existente.>

### 3.2 <Próximo componente, se houver>
<...continuar para cada parte da solução...>

## 4. Fluxo após a correção
<Diagrama ASCII do fluxo>

## 5. Arquivos a modificar/criar
| Arquivo | Tipo de mudança |
|---|---|
| `src/...` | Modificar — <descrição concisa> |
| `src/...` | Criar — <descrição concisa> |

## 6. Critérios de Aceite
- [ ] <critério verificável e objetivo>
- [ ] <critério verificável e objetivo>
- [ ] `bun run build` passa sem erros.

## 7. Considerações adicionais
<Segurança, performance, acessibilidade, débito técnico futuro ou dependências externas. Omitir se não houver.>

Regras de qualidade do SDD:
- Snippets sempre completos e compiláveis.
- Referências ao código atual com número de linha quando alterar código existente.
- Sem ambiguidade.
- Escopo cirúrgico.

FASE 2 — Validação do SDD

Faça auto-revisão:
- [ ] Todos os arquivos da seção 5 existem (ou são explicitamente novos)?
- [ ] Snippets compatíveis com versões usadas no projeto?
- [ ] Critérios de aceite verificáveis objetivamente?
- [ ] Escopo claro, sem ambiguidade?

Corrija inconsistências antes de prosseguir.

Apresente resumo (3–5 linhas) e pergunte: "O SDD está correto? Posso gerar as tasks?"

FASE 3 — Geração das Tasks

Após aprovação do SDD, criar tasks em `docs/<nome-da-feature>/tasks/`.

Nomenclatura:
TASK-1-<descricao-em-kebab-case>.md
TASK-2-<descricao-em-kebab-case>.md
...
TASK-N-verificacao-e2e.md (sempre a última)

Estrutura de cada task:
# TASK-N — <Descrição>

**Arquivo alvo:** `src/...` (novo | existente)
**Referência SDD:** Seção X.Y
**Depende de:** TASK-X, TASK-Y | nenhuma
**Bloqueada por:** TASK-X | nenhuma

## Contexto
## O que fazer
## Notas de implementação
## Critério de aceite
- [ ] <verificação objetiva>
- [ ] `bun run build` passa sem erros.

Regras:
1. Granularidade por arquivo alterado/criado significativo.
2. Paralelismo explícito.
3. Ordem de dependência executável.
4. Task final obrigatória de verificação e2e.
5. Snippets completos.
6. Sem task de documentação.

Quantidade de tasks:
- 1 arquivo significativo = 1 task (em geral)
- Várias mudanças pequenas no mesmo arquivo = 1 task
- Sempre incluir verificação e2e ao final

FASE 4 — Resumo final

✓ SDD: docs/<feature>/SDD.md
✓ Tasks: docs/<feature>/tasks/
   TASK-1 — <descrição>         [independente]
   TASK-2 — <descrição>         [após TASK-1]
   ...
   TASK-N — Verificação e2e     [última]

Paralelas: TASK-X e TASK-Y podem ser executadas simultaneamente.

Referências de padrão:
- docs/lgpd-consent-terms/SDD.md
- docs/lgpd-cookie-consent/SDD.md
- tasks nas pastas correspondentes
```

## Exemplos de entrada

- `/spec Corrigir validação de formulário de cadastro que aceita e-mail inválido`
- `/spec Adicionar autenticação 2FA via e-mail para usuários administradores`

## Exemplos de saída

- `docs/autenticacao-2fa/SDD.md` com contexto, escopo, design, fluxo, critérios de aceite.
- `docs/autenticacao-2fa/tasks/TASK-1-...md` até `TASK-N-verificacao-e2e.md` com dependências explícitas.

## Casos de uso

- Planejar features antes da implementação.
- Quebrar correções críticas em tarefas executáveis por múltiplos devs/agentes.
- Reduzir ambiguidade técnica em PRs grandes.

## Limitações

- Depende de contexto correto do usuário para precisão.
- Pode exigir ajustes para stacks não TypeScript.
- Não substitui revisão técnica humana.

## Boas práticas

- Forneça contexto de negócio e risco na FASE 0.
- Valide e aprove o SDD antes de gerar tasks.
- Use nomes de feature curtos e claros em kebab-case.
- Revise critérios de aceite com foco em verificabilidade.
