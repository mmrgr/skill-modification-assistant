# Example: Public Release Review

## User Request

```text
Check whether this skill is safe to publish.
Target: /skills/internal-reporting/SKILL.md
```

## Diagnosis

- Issue type: release-readiness and privacy review.
- Likely risks: private paths, customer names, internal APIs, unsupported capability claims, missing license.

## Recommended Option

Release Readiness.

## Change Pattern

- Replace private paths with placeholders.
- Remove tokens, account names, private URLs, and customer identifiers.
- Check examples, fixtures, assets, and README claims.
- Ensure license status is explicit.
- Keep internal-only behavior labeled or remove it from the public version.

## Expected Result

The public skill contains only publishable examples, accurate claims, and clear licensing.

