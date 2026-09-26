# Word QA Checklist v1.1

All blocking checks must pass. A checked box requires current evidence from the delivered file, not a prior document or an assumed library default.

## A. Source and package

- [ ] **BLOCKING** The source/reference DOCX remains unchanged and its SHA-256 is recorded when editing.
- [ ] **BLOCKING** DOCX ZIP integrity passes with no corrupt package parts.
- [ ] **BLOCKING** The output reopens through an independent DOCX reader.
- [ ] Package relationships, headers, footers, fields, numbering and preserved opaque parts are present as expected.

## B. Page and cover

- [ ] **BLOCKING** Page size, orientation and margins match `WORD_TOKENS.json` unless an approved exception is recorded.
- [ ] The cover remains on the different first page and has no normal header, footer or page number.
- [ ] The cover follows the unchanged v1.0 cover system; body spacing rules were not applied to it.
- [ ] Major chapters use real page breaks rather than repeated blank paragraphs.

## C. Typography and spacing

- [ ] **BLOCKING** All four font mappings are present: `ascii=Aptos`, `hAnsi=Aptos`, `eastAsia=仿宋`, `cs=Aptos`.
- [ ] **BLOCKING** Every body-region paragraph uses `1.5×` line spacing (`w:line=360`, `w:lineRule=auto`).
- [ ] **BLOCKING** Every body-region paragraph has equal before and after spacing; group-ending zero spacing is `0/0`.
- [ ] Heading sizes, body sizes, indents, bold and keep behavior match their role tokens.
- [ ] **BLOCKING** Every explanatory/boundary-note run, including punctuation and Latin fragments, is italic and exactly `9 pt` (`w:sz=18`; `w:szCs=18` when present).

## D. Bullets

- [ ] **BLOCKING** Bullets are real Word lists with `w:numPr`; no typed bullet, hyphen or dash is used as a substitute.
- [ ] **BLOCKING** Each effective level-0 bullet definition has `numFmt=bullet`, `lvlJc=left`, `w:left=360` and `w:hanging=360`.
- [ ] Bullet position is the content-area left edge; item text starts `0.635 cm` from that edge.
- [ ] Bullet text is `11 pt`, regular, at `1.5×` line spacing.
- [ ] Normal bullet spacing is `3.25/3.25 pt`; a closing item may use `0/0 pt`.

## E. Header footer tables and flow

- [ ] Header and footer content belongs to the current document and contains no inherited names.
- [ ] Page numbering uses a live `PAGE` field, not fixed text.
- [ ] Titles remain with the following paragraph; no isolated headings are rendered at page bottoms.
- [ ] Table rows do not split across pages; table widths, wrapping and cell margins are deliberate.
- [ ] No content is clipped, overlapped, hidden or forced into an abnormal blank page.

## F. Visual and content verification

- [ ] **BLOCKING** Every page was rendered after the final material change and inspected at 100%.
- [ ] **BLOCKING** Missing fonts or substitutions are recorded; final font fidelity is not claimed when the renderer lacks the required fonts.
- [ ] Facts, names, dates, partners, metrics, quotations and commitments are verified or marked unresolved.
- [ ] All approved deviations are listed in the completion report.

## Required completion result

```text
Standard: Word Document Standard v1.1
Pinned commit: <FULL_COMMIT_SHA>
Document: <filename>
Package integrity: PASS | FAIL
Structural QA: PASS | FAIL
Visual QA: PASS | FAIL | LIMITED
Exceptions: none | <short list>
```
