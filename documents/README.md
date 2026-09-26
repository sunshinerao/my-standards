# Word Document Standards

This module is the canonical Word standard for documents generated under the fixed trigger `按照规范生成`.

It is designed for two readers at the same time:

- humans use `WORD_DESIGN_SYSTEM.md` to understand the visual and editorial rules;
- agents and document builders use `WORD_TOKENS.json` and `AI_BUILD_RULES.md` to implement them exactly.

## Required reading order

1. `README.md`
2. `WORD_DESIGN_SYSTEM.md`
3. `WORD_TOKENS.json`
4. `AI_BUILD_RULES.md`
5. `QA_CHECKLIST.md`

The fixed startup prompt is `../prompts/word_AGENT_START.md`.

## Authority and precedence

Within an authorized document task, precedence is:

1. the user's explicit instruction in the current task;
2. an explicitly approved project exception;
3. `WORD_TOKENS.json` for exact machine values;
4. `WORD_DESIGN_SYSTEM.md` for meaning and usage;
5. `AI_BUILD_RULES.md` for implementation behavior;
6. agent defaults.

If the prose and token file disagree, stop and report the conflict. Do not choose a value silently.

## Current calibration

Document Standards v1.1 incorporates the previously approved V1.0 system plus these confirmed revisions:

- body-region paragraphs use 1.5 line spacing;
- each paragraph's spacing before and after is symmetric; different paragraph roles may use different values, and the final paragraph in a group may use `0 pt / 0 pt`;
- italic explanatory notes use exactly `9 pt`;
- level-0 bullets use a text indent of `0.635 cm` and a hanging indent of `0.635 cm`, placing the bullet at the content-area left edge and the item text `0.635 cm` from that edge.

The cover system is unchanged by these revisions.

## Files

| File | Purpose |
|---|---|
| `WORD_DESIGN_SYSTEM.md` | Human-readable normative specification |
| `WORD_TOKENS.json` | Machine-readable values and OOXML mappings |
| `AI_BUILD_RULES.md` | Required generation and editing behavior |
| `QA_CHECKLIST.md` | Blocking acceptance checklist |
| `VALIDATION_REPORT.md` | Evidence from the calibration DOCX audit |

## Fixed activation command

```text
Use Word Document Standard v1.1.
Read and obey sunshinerao/my-standards before creating or editing the document.
Trigger: 按照规范生成
```

Production projects should pin this repository to a full commit SHA.
