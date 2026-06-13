# Example: Confirmation Gate Hardening

## User Request

```text
Make this skill ask before it edits files.
Target: /skills/file-helper/SKILL.md
```

## Diagnosis

- Issue type: confirmation-flow issue.
- Likely cause: the skill can write or overwrite files after diagnosis without a final confirmation step.
- Risk: persistent changes happen after vague approval.

## Recommended Option

Safety Hardening.

## Change Pattern

- Add a live-write confirmation gate.
- Define valid and insufficient confirmations.
- Require the agent to restate target file scope before editing.
- Add a test where "sounds good" must not trigger a write.

## Expected Result

The skill may read, summarize, and propose automatically, but it cannot modify live files until the user clearly confirms.

