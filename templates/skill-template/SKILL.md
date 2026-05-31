---
name: my-skill
description: Help with X workflow for Y context. Use when the user asks about X, mentions Y, or needs this recurring procedure.
---

# My Skill

Use this skill to apply a focused, reusable workflow.

## What this skill does

Describe the outcome this skill is meant to produce.

## When to use

- Use when the request matches the workflow described in `description`.
- Use when the user needs a repeatable procedure instead of generic advice.

## When not to use

- Do not use when a simpler direct answer is enough.
- Do not use when another skill is clearly more specialized.

## Inputs needed

- Required context
- Relevant files, URLs, or constraints
- Expected output format

## Procedure

1. Gather only the context needed to start.
2. Check assumptions and constraints.
3. Execute the workflow in a deterministic order.
4. Validate the result before finishing.

## Validation

- The expected artifact exists.
- The output matches the user's request.
- Any checks or tests relevant to the workflow have been run.

## Common failure modes

- Missing context
- Wrong assumptions
- Skipping validation

## Supporting files

- Put long guidance in `references/`
- Put reusable artifacts in `templates/`
- Put deterministic helpers in `scripts/`
- Put static files in `assets/`
