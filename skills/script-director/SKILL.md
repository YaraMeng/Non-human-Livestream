# script-director

## Purpose

Convert a raw Discord idea into a structured production plan for downstream rendering.

## Input

- Free-form prompt from user
- Optional character/style constraints

## Output

Structured plan containing:

- title
- global style
- scene list
- per-scene visual prompt
- per-scene motion/camera hint
- per-scene audio direction

## Responsibilities

1. Clarify ambiguous prompts.
2. Produce scene-by-scene plan.
3. Keep output deterministic and machine-readable.

## Handoff contract

The output must match the schema used by:

- `skills/discord-workflow/references/example.yaml`

## Safety constraints

- Do not include secrets in output.
- Do not emit unsafe or policy-violating content.
