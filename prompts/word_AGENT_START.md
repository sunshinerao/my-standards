# Word Agent Start

Copy this instruction into a new project or task:

```text
Use Word Document Standard v1.1.
Trigger: 按照规范生成

Before creating or editing any Word document:

1. Read the root README.md and AGENTS.md in sunshinerao/my-standards.
2. Read, in order:
   - documents/README.md
   - documents/WORD_DESIGN_SYSTEM.md
   - documents/WORD_TOKENS.json
   - documents/AI_BUILD_RULES.md
   - documents/QA_CHECKLIST.md
3. Treat these files as normative constraints, not visual inspiration.
4. Use WORD_TOKENS.json for exact values and WORD_DESIGN_SYSTEM.md for meaning.
5. Preserve an existing DOCX package and make minimal edits when the task is a revision.
6. Keep the cover unchanged unless the current task explicitly authorizes a cover change.
7. In the body region, use 1.5 line spacing and equal spacing before and after each paragraph.
8. Set every italic explanatory or boundary note to exactly 9 pt.
9. Build bullets as real Word lists with level-0 left=360 twips and hanging=360 twips.
10. Validate package structure, reopen the output, render every page, inspect every page at 100%, and complete documents/QA_CHECKLIST.md.
11. Do not claim font fidelity if the renderer substitutes a required font.
12. Report:
    Standard
    Pinned commit
    Document
    Package integrity
    Structural QA
    Visual QA
    Exceptions

Current explicit user instructions override the standard only for the named scope. Record every approved exception. Do not invent missing facts or silently approximate token values.
```
