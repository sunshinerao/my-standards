# Word AI Build Rules v1.1

These rules are binding whenever the user says `按照规范生成` or explicitly invokes Word Document Standard v1.1.

## 1. Load the authority before editing

Read, in order:

1. root `README.md` and `AGENTS.md`;
2. `documents/README.md`;
3. `documents/WORD_DESIGN_SYSTEM.md`;
4. `documents/WORD_TOKENS.json`;
5. this file;
6. `documents/QA_CHECKLIST.md`.

Do not reconstruct the standard from memory. Pin the repository to a full commit SHA for production work.

## 2. Determine the task before formatting

Identify the document type, reader, purpose, language, cover requirement, title, date, confidentiality status and required header/footer text. Treat unconfirmed facts as unresolved, not as permission to invent them.

When editing an existing DOCX:

- preserve the source package and make the smallest safe change;
- preserve sections, relationships, fields, headers, footers, styles and opaque package parts unless the task requires a change;
- do not resave the entire package through a different library when a targeted OOXML edit is sufficient;
- keep an untouched source copy and compare package parts after the edit.

## 3. Apply exact tokens

- Use `WORD_TOKENS.json` values exactly; do not round to a visually similar value.
- Write all four font mappings: `ascii`, `hAnsi`, `eastAsia`, `cs`.
- Use `w:spacing w:line="360" w:lineRule="auto"` for body-region `1.5×` line spacing.
- For every body-region paragraph, set equal before and after spacing. If closing a group, use `0/0`, not a one-sided zero.
- Keep the cover's v1.0 spacing unchanged. Do not apply body spacing symmetry or 1.5× line spacing to the cover.
- Set every explanatory or boundary note to exactly `9 pt` and italic. Write `w:sz=18` and, when complex-script size is present, `w:szCs=18`. Verify every run in every note, including punctuation and mixed Latin text.

## 4. Build bullets as Word structures

For each level-0 bullet definition:

```xml
<w:numFmt w:val="bullet"/>
<w:lvlJc w:val="left"/>
<w:ind w:left="360" w:hanging="360"/>
```

Required interpretation:

- bullet position: content-area left edge;
- item text position: `360 twips` or `0.635 cm` from that edge;
- hanging indent: `360 twips` or `0.635 cm`;
- list paragraph must contain `w:numPr`; do not type the marker into `w:t`.

The paragraph style alone is not evidence that a real list exists. Resolve `numId` to `abstractNumId`, then verify the effective level definition in `word/numbering.xml`.

## 5. Preserve structure

- Use explicit page breaks for major chapters.
- Use `keepNext` for chapter titles, secondary headings and numbered item headings.
- Use a live `PAGE` field for page numbering.
- Use a different first page for the cover.
- Prevent table rows from splitting across pages.
- Do not use repeated empty paragraphs for positioning or pagination.

## 6. Validate the package

Before delivery:

1. Confirm the DOCX ZIP package has no errors.
2. Reopen it with an independent DOCX reader.
3. Inspect `document.xml`, `styles.xml`, `numbering.xml`, section properties, header/footer parts and relationships as relevant.
4. Run the full `QA_CHECKLIST.md`.
5. Render every page to images and inspect every page at 100%.
6. If required fonts are unavailable in the renderer, record the substitution as an environment limitation and do not claim final font-fidelity verification.
7. Revise and rerender after every material formatting change.

## 7. Completion report

Report only confirmed facts:

```text
Standard: Word Document Standard v1.1
Pinned commit: <FULL_COMMIT_SHA>
Document: <filename>
Package integrity: PASS | FAIL
Structural QA: PASS | FAIL
Visual QA: PASS | FAIL | LIMITED
Exceptions: none | <short list>
```

Any blocking item in `QA_CHECKLIST.md` means the document is not complete.
