# Naming Checklist

## Global

- Use English names only.
- Keep one naming convention consistent in the same scope.
- Pass S-I-D: short, intuitive, descriptive.
- Avoid contractions and unclear abbreviations.
- Avoid context duplication (remove what the scope already implies).

## Booleans

- Prefer `isX` for state/characteristic.
- Prefer `hasX` for possession/existence.
- Prefer `shouldX` for conditional + action.
- Prefer names that match the consuming API directly (expected result).

## Functions

- Follow A/HC/LC: prefix? + action + highContext + lowContext?
- Use established actions: get/set/reset/remove/delete/compose/handle.
- Ensure context order matches the intended meaning.
- For callbacks/handlers, prefer `handle…` (or the project’s existing handler verb).

## Collections & Numbers

- Use singular for a single value, plural for multiple values.
- Use `min`/`max` for boundaries/limits.
- Use `prev`/`next` for state transitions.

