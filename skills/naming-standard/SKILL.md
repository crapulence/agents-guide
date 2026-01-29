---
name: naming-standard
description: Apply a practical naming standard (from naming-cheatsheet) to generate naming suggestions, renaming proposals, and naming reviews for variables/functions/callbacks/booleans/collections. Use for English naming, consistent convention, S-I-D, no contractions, avoiding context duplication, boolean expected-result naming, A/HC/LC function naming, action verbs (get/set/reset/remove/delete/compose/handle), prefixes (is/has/should/min/max/prev/next), and singular/plural rules.
---

# Naming Standard

Use this skill to produce names that are short, readable, and semantically accurate.

If you need the original source material, read:
- references/naming-cheatsheet.md
- references/checklist.md

## Workflow

For each identifier that needs naming (new or rename), follow this workflow.

### 1) Build a naming brief

Collect these fields first:
- Kind: variable | constant | boolean | collection | function | callback | class | component
- Meaning: what it represents or does (one sentence)
- Context: enclosing module/class/component and domain (used to avoid duplication)
- Effects: pure vs side effects; sync vs async
- Constraints: must keep existing API? must match project naming convention?

If the request includes code, infer the project convention from nearby identifiers. If you cannot infer it, default to:
- camelCase for variables/functions
- PascalCase for classes/components
- UPPER_SNAKE_CASE for constants

### 2) Generate candidates (3–5)

Generate 3–5 candidates first, then pick a recommended one.

Apply these rules while generating candidates:
- English only.
- Keep one naming convention consistent within the same scope.
- Use S-I-D: short, intuitive, descriptive.
- Avoid contractions and cryptic abbreviations.
- Avoid context duplication: do not repeat what the scope already provides.

### 3) Choose the correct pattern by kind

#### Booleans

Name booleans to reflect the expected result. Prefer names that match the consuming API directly.
- Prefer `isDisabled` over `isEnabled` + negation when passing to `disabled={...}`.
- Prefer `hasX` for possession/existence, not `isXExist`.
- Prefer `shouldX` for condition + action.

#### Functions

Name functions using A/HC/LC:

prefix? + action + highContext + lowContext?

Guidelines:
- Use a clear verb as the action.
- Put the most meaningful context closer to the action (high context first).
- For callbacks/event handlers, prefer `handle…` for the action.
- Do not make up verbs. Use established actions.

Action verb semantics:
- `getX`: access/return data.
- `setX`: set a value (A → B).
- `resetX`: return to initial state.
- `removeX`: remove from a collection/destination.
- `deleteX`: permanently erase.
- `composeX`: create new data from existing data.
- `handleX`: callback/handler for an interaction or event.

#### Collections

Use plural names for collections and singular for single values.
- `friends` for `Friend[]`
- `friend` for `Friend`

### 4) Produce the final answer (strict output format)

For each identifier, output:
- Recommended name (1)
- Alternatives (1–3)
- Rationale (map each reason to a specific rule)
- Avoid (anti-examples and why)

Use this template:

#### <currentName or “(new)”> — <kind>
- Recommended: `<name>`
- Alternatives: `<name>`, `<name>`
- Rationale: S-I-D; no contractions; no context duplication; expected-result boolean; A/HC/LC; correct action verb; correct singular/plural
- Avoid: `<badName>` (reason), `<badName>` (reason)

### 5) Final review

Run the checklist in references/checklist.md and fix any violations.

