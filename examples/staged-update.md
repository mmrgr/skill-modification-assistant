# Example: Staged Update

## User Request

```text
Stage this update first. Do not overwrite the live skill.
Target: /skills/research-helper/SKILL.md
```

## Diagnosis

- Issue type: broad or review-first change.
- Likely cause: the user wants a safe review artifact rather than a live patch.
- Risk: direct editing would make review and rollback harder.

## Recommended Option

Staged Evolution.

## Change Pattern

Create a package such as:

```text
skill-updates/2026-06-13/research-helper/
+-- SKILL.md
+-- rationale.md
+-- tests.md
`-- handoff.md
```

The live `/skills/research-helper/SKILL.md` remains unchanged.

## Expected Result

The user can review the staged package and later explicitly approve applying it to the live skill.

