# Diamondneed to Diamond Build Handoff

This file defines the handoff contract between Diamondneed-skill and Diamond Build Skill.

Diamondneed-skill should not only output demand analysis. When the conclusion is Go or Wait-to-Test, it should produce a compact handoff for development planning.

---

## Handoff Template

```md
# Demand-to-Build Handoff

## 1. Demand Name

## 2. Go / Wait / No-Go Conclusion

## 3. Target User

## 4. User Core Pain Point

## 5. Why the User Would Pay

## 6. Market Signals Observed

- platform:
- competitor:
- sales/traffic/comments:
- user feedback:

## 7. Recommended First SKU

- SKU name:
- price range:
- delivery model:
- payment model:
- why this SKU first:

## 8. Recommended First Product Shape

Examples:

- web tool
- AI generator
- WordPress resource site
- auto card-key system
- desktop app
- admin tool
- manual service + tool support

## 9. First-Version Core Workflow

Describe the one core flow that must work first.

## 10. Must-have Features

List only 3-7 features.

## 11. Do-not-build Features

List features that should be explicitly excluded from v0.1.

## 12. Key Risks

- payment risk:
- copyright/content risk:
- delivery risk:
- platform risk:
- AI cost risk:
- customer-service risk:

## 13. Development Constraints

- time:
- budget:
- preferred stack:
- deployment:
- payment:
- file/storage:
- AI model:

## 14. Notes for Diamond Build Skill

Any special context that must not be lost during development planning.
```

---

## Handoff Quality Rules

A good handoff should be compact but decisive.

It should not say:

> “This can be a platform with many features.”

It should say:

> “First version should be a web tool with one generation flow, card-key activation, generation history, and a small admin panel. Do not build reseller, subscription, or advanced analytics in v0.1.”

---

## Why this handoff matters

Without a handoff, Diamond Build Skill may overbuild.

The handoff preserves:

- commercial judgment
- first SKU choice
- delivery model
- scope limits
- risks
- user payment logic

The build spec should inherit these decisions unless there is a clear architecture reason to change them.
