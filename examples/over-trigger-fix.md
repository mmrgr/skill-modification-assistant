# Example: Over-Trigger Fix

## User Request

```text
This skill triggers whenever I discuss prompt engineering. Please fix it.
Target: /skills/prompt-editor/SKILL.md
```

## Diagnosis

- Issue type: trigger boundary problem.
- Likely cause: the frontmatter description says "prompt editing" without requiring an explicit skill-editing intent.
- Risk: ordinary discussion activates a file-edit workflow.

## Recommended Option

Conservative Patch.

## Change Pattern

- Tighten frontmatter to require an existing `SKILL.md`, staged update, observation log, or explicit skill-maintenance request.
- Add non-trigger cases for general prompt discussion.
- Preserve the existing edit workflow.

## Expected Result

The skill triggers for "modify `/skills/a/SKILL.md`" but not for "let's discuss prompt engineering."

