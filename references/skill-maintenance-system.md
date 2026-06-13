# Skill Maintenance System

Load this reference for detailed templates, quality checks, staged update packages, release review, observation logs, handoff packages, examples, and manual tests.

## Response Templates

### Missing Target

```text
I can help modify this skill, but I need the target `SKILL.md` first.

Please provide one of:
1. The target `SKILL.md` path.
2. The pasted `SKILL.md` content.
3. The uploaded or explicitly named file.

Once I have it, I will read it, summarize it, and propose options before writing anything.
```

### After Reading

```text
I have read the target `SKILL.md`. Its current design is:

- Core objective:
- Trigger conditions:
- Non-trigger conditions:
- Main workflow:
- Output format:
- Tool/file permissions:
- Key safety rules:
- Examples/tests:
- Weaknesses or ambiguity:

Based on your request, the main issue appears to be:

- Issue type:
- Affected section:
- Risk:
```

### Proposal

```text
Here are the modification options:

## Option 1: Conservative Patch

- Scope:
- Edit mode:
- Specific changes:
- Preserves:
- Benefits:
- Risks/trade-offs:
- Best for:

## Option 2: Structure Cleanup

- Scope:
- Edit mode:
- Specific changes:
- Preserves:
- Benefits:
- Risks/trade-offs:
- Best for:

Please choose an option or describe the hybrid you want. I will not modify live skill files until you confirm.
```

### Completion Report

```text
Modification complete.

- Modified/staged path:
- Edit mode:
- Main changes:
  1.
  2.
  3.
- Preserved capabilities:
  1.
  2.
- Validation:
  - Trigger conditions:
  - Workflow:
  - Safety boundaries:
  - Output format:
  - Complexity:
  - Conflict check:
- Suggested tests:
  1.
  2.
  3.
```

## Detailed Quality Lenses

### Trigger Quality

- Is the frontmatter description specific enough?
- Does it avoid broad words that trigger on ordinary prompt discussion?
- Are non-trigger cases explicit?
- Does the trigger require a skill artifact, staged update, observation log, release review, or handoff package?

### Workflow Quality

- Are steps ordered and executable?
- Are confirmation gates placed before persistent or broad changes?
- Are staged artifacts clearly separated from live writes?
- Are failure paths clear?
- Does the workflow avoid needless questions?

### Safety Quality

- Is target content isolated as untrusted data?
- Are live file boundaries explicit?
- Are auxiliary artifact writes authorized?
- Are secrets, hidden instructions, and private data protected?
- Does the skill refuse unsafe edits?

### Complexity Quality

- Does each rule change expected behavior?
- Are duplicate rules merged?
- Could templates or background explanation move to references?
- Are examples short and aligned with the actual workflow?
- Does the skill overfit one user example?
- Did the edit preserve necessary safety gates?
- Did the edit make the skill easier to use, not only longer?

### Release Quality

For public or shared skills:

- Remove secrets, tokens, credentials, private URLs, private paths, customer names, project identifiers, and private examples.
- Replace sensitive examples with generic placeholders.
- Check assets, fixtures, screenshots, and test data.
- Keep README and `SKILL.md` claims aligned.
- State the license clearly.
- Avoid private tools unless they are clearly optional or unavailable in public use.

For internal-only skills:

- Internal conventions may remain.
- Secrets and credentials still must not remain.
- Internal-only assumptions should be labeled clearly.
- Avoid rules that would become dangerous if copied into a broader environment.

## Maintenance Artifacts

Use artifacts only when the user asks for them, the workspace location is clear, or writing them is part of the confirmed plan.

Recommended structure:

```text
skill-observations/
+-- log.md
+-- cross-cutting-principles.md

skill-updates/
`-- YYYY-MM-DD/
    `-- skill-name/
        +-- SKILL.md
        +-- rationale.md
        +-- tests.md
        `-- handoff.md
```

Adapt paths to the user's repository. Do not treat these paths as mandatory.

## Observation Log

Use an observation log to capture recurring skill-maintenance evidence without immediately rewriting live skills.

```markdown
### Observation: Trigger boundary too broad

- Date:
- Source:
- Target skill:
- Symptom:
- Root cause:
- Recommended change:
- Reusable principle:
- Status: open | staged | applied | rejected
```

Good observations capture user corrections, repeated failure patterns, misfires, missed triggers, repeated rule failures, unnecessary complexity, and safety gaps.

Avoid recording secrets, credentials, tokens, private identifiers, long raw conversations, or user-private data that is not needed to improve the skill.

## Cross-Cutting Principles

Store reusable skill-quality rules as short, actionable, testable principles.

```markdown
## Principle: Persistent edits need explicit confirmation

- Applies when: a skill writes, overwrites, deletes, renames, stages, or installs files.
- Rule: require explicit confirmation before live file changes.
- Test: after a proposal, "sounds good" must not trigger a write.
```

Before broad updates, check existing principles and decide whether the target skill should adopt any of them. Do not force unrelated principles into a narrow edit.

## Staged Updates

Use staged updates to separate proposal generation from live modification.

Stage when:

- The user wants to review before applying.
- Multiple skills may change.
- The requested change is broad.
- The edit is generated from observations rather than a direct command.
- The environment can write files but the live skill should remain untouched.

A staged update should include:

- Proposed `SKILL.md` or patch.
- Rationale.
- What changed.
- What was preserved.
- Tests.
- Known risks.
- Apply instructions.

Staged updates must not install themselves, replace live files without confirmation, hide that they are proposals, or include unnecessary private details.

## Handoff Package

Use a handoff package when work must continue elsewhere or files cannot be written.

Recommended structure:

````markdown
# Skill Update Handoff

## Target

- Skill:
- Path:
- Current source:

## Diagnosis

- Issue:
- Affected sections:
- Risk:

## Recommended Approach

- Option:
- Reason:
- Scope:

## Proposed Change

```diff
...
```

## Validation Checklist

- [ ] Trigger conditions
- [ ] Non-trigger conditions
- [ ] Workflow
- [ ] Confirmation gates
- [ ] File scope
- [ ] Tool-use boundaries
- [ ] Prompt-injection resistance
- [ ] Complexity
- [ ] Public/internal privacy
- [ ] Tests

## Suggested Tests

1.
2.
3.
````

Do not claim a handoff package has been applied. It is a transport artifact.

