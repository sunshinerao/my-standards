# Word Document Design System v1.1

## 1. Scope and trigger

This standard applies to `.docx` reports, proposals, policies, manuals, invitations, training materials, technical documents and attachments.

The fixed trigger is:

```text
按照规范生成
```

When triggered, the standard governs page setup, typography, spacing, cover, hierarchy, lists, tables, headers, footers, pagination and delivery QA. A current explicit user instruction overrides the default only for the scope the user names.

## 2. Visual character

Use a black-and-white, restrained, high-whitespace institutional style. Establish hierarchy through typography, spacing, indentation and numbering, not decoration.

- Text, rules, numbering and table text: `#000000`.
- Page background: white.
- Do not introduce theme blue, accent colors, gradients, shadows or decorative color blocks unless the user explicitly requests them.
- Avoid dense walls of text and do not force content into the bottom of a page.

## 3. Page system

- Default page: A4 portrait, `21.00 × 29.70 cm`.
- Margins: top `2.55 cm`, bottom `2.35 cm`, left `2.70 cm`, right `2.70 cm`.
- Header distance: `1.00 cm`.
- Footer distance: `1.00 cm`.
- Use a different first page so the cover has no normal header, footer or page number.
- Use a landscape section only for a genuinely wide table, drawing or similar content, and only when required.

## 4. Font mapping

- Chinese and East Asian text: `仿宋` through the OOXML `eastAsia` mapping.
- Latin text, Arabic numerals, symbols and Western punctuation: `Aptos` through `ascii`, `hAnsi` and `cs`.
- Write all four OOXML font mappings. Setting only a generic run font is insufficient.

## 5. Cover system

The cover is unchanged from v1.0. Use a centered, text-only composition without placeholder logos, decorative frames, color images, QR codes or page numbers.

| Role | Size and treatment | Paragraph settings |
|---|---|---|
| Top eyebrow | Aptos `8.5 pt`, bold, uppercase | Centered, single line spacing, `0/70 pt` before/after |
| Document property line | Chinese `15 pt`, regular | Centered, about `1.03×`, `0/12 pt` |
| Chinese main title line 1 | 仿宋 `29 pt`, bold | Centered, about `1.04×`, `0/8 pt` |
| Chinese main title line 2 | 仿宋 `29 pt`, bold | Centered, about `1.04×`, `0/18 pt` |
| English title line 1 | Aptos `11 pt`, bold, uppercase | Centered, single, `0/4 pt` |
| English title line 2 | Aptos `10.5 pt`, bold, uppercase | Centered, single, `0/35 pt` |
| Chinese subtitle line 1 | 仿宋 `12.5 pt`, regular | Centered, `1.20–1.25×`, `0/5 pt`; optional `0.40 cm` side indents |
| Chinese subtitle line 2 | 仿宋 `12.5 pt`, regular | Centered, `1.20–1.25×`, `0/77 pt` |
| Bottom label | Aptos `8.5 pt`, bold, uppercase | Centered, single, `0/4 pt` |
| Version or date | Aptos `9 pt`, regular | Centered, single, `0/0 pt` |

Cover spacing is intentionally asymmetric and is exempt from the body-region symmetric-spacing rule.

## 6. Body rhythm and paragraph spacing

All text in the body region, including headings, numbered items, lists, explanatory notes and table text, uses `1.5×` line spacing.

For every body-region paragraph, `space before` must equal `space after`. This is a per-paragraph symmetry rule, not one global spacing value. The final paragraph in a tightly related group may use `0 pt / 0 pt`; it must not use `x pt / 0 pt`.

Recommended role values calibrated from the reference document:

| Role | Before / after |
|---|---:|
| Section English eyebrow | `2.5 / 2.5 pt` |
| Chinese chapter title | `9 / 9 pt` |
| Chapter introduction | `7.5 / 7.5 pt` |
| Secondary heading | `7.5 / 7.5 pt` |
| Numbered item heading | `2 / 2 pt` |
| Numbered item explanation | `5 / 5 pt` |
| Bullet item | `3.25 / 3.25 pt` |
| Italic explanatory note | `4 / 4 pt` |
| Emphasis statement | `15 / 15 pt` |
| Final paragraph in a group | `0 / 0 pt` |

## 7. Heading hierarchy

Major chapters begin on a new page. A heading must remain with the first following paragraph.

| Role | Typography | Layout |
|---|---|---|
| Section English eyebrow | Number Aptos `10 pt` bold; label Aptos `8.5 pt` bold uppercase | Left; `1.5×`; `2.5/2.5 pt` |
| Chinese chapter title | 仿宋 `21 pt` bold | Left; `1.5×`; `9/9 pt`; keep with next |
| Secondary heading | 仿宋 `13 pt` bold | Left; `1.5×`; `7.5/7.5 pt`; keep with next |
| Numbered item heading | Number and title `12.5 pt` bold | Left; `1.5×`; `2/2 pt`; keep with next |
| Continuous numbered list | Number `11.5 pt` bold; text `11.5 pt` regular | `1.5×`; use symmetric spacing |

Use real page breaks, not repeated blank paragraphs.

## 8. Body text and emphasis

| Role | Typography | Layout |
|---|---|---|
| Standard body | 仿宋 `11.5 pt`, regular | Left; first-line indent `0.80 cm`; `1.5×`; symmetric spacing |
| Chapter introduction | 仿宋 `12 pt`, regular | First-line indent `0.80 cm`; `1.5×`; `7.5/7.5 pt` default |
| Numbered item explanation | 仿宋 `10.5 pt`, regular | Left indent `1.05 cm`; no first-line indent; `1.5×`; `5/5 pt` |
| Emphasis statement | 仿宋 `14–15 pt`, bold | Left and right indents `0.75 cm`; `1.5×`; `15/15 pt`; normally no more than one per page |
| Explanatory or boundary note | 仿宋 `9 pt`, italic | Left; no first-line indent; `1.5×`; `4/4 pt` |

The `9 pt` explanatory-note value is exact. Do not inherit `10.5 pt` from the v1.0 rule or from adjacent body runs.

## 9. Bullet list system

Use a real Word numbering definition with `numFmt=bullet`. Never type a hyphen, dash or bullet character into the paragraph text to simulate a list.

For level-0 bullets:

- body text: 仿宋 `11 pt`, regular;
- line spacing: `1.5×`;
- normal item spacing: `3.25/3.25 pt`;
- final item spacing: `0/0 pt` when closing the group;
- text position from content-area left edge: `0.635 cm`;
- hanging indent: `0.635 cm`;
- bullet position: `0 cm` from the content-area left edge;
- marker: standard solid round bullet, left aligned.

OOXML implementation for the list level:

```xml
<w:numFmt w:val="bullet"/>
<w:lvlJc w:val="left"/>
<w:ind w:left="360" w:hanging="360"/>
```

`360 twips = 18 pt = 0.25 in = 0.635 cm`. Both `left` and `hanging` are required. Do not translate this rule back to the v1.0 values of `0.80 cm` left and `0.35 cm` hanging.

## 10. Header footer and pagination

- First page: no normal header, footer or page number.
- Header text: left aligned `Institution or document type | English topic`; Aptos `7.5 pt`, first part bold and second part regular.
- Header rule: `0.5 pt` black single line beneath the header; no colored or double rule.
- Footer left: owning name and short title, `7.5 pt`, left aligned.
- Footer right: a live Word `PAGE` field, Aptos `8 pt`, right aligned.
- Enable widow and orphan control.
- Keep chapter titles, secondary headings and numbered item headings with their first following paragraph.

## 11. Tables and figures

- Use tables only when readers need to compare structured values across rows or columns.
- Use black text and thin black or neutral-gray borders; no decorative fill.
- Map Chinese to 仿宋 and Latin text to Aptos.
- Keep table text at `1.5×` line spacing.
- Make header text bold.
- Do not allow a single row to split across pages.
- Use deliberate column widths and cell margins; do not autosize blindly.
- Use only black, white and grayscale in charts unless the user explicitly authorizes color.
- State source, year and unit when a chart uses data.

## 12. Content integrity and exceptions

- Do not invent institutions, partners, dates, metrics, quotations or commitments.
- Keep verified fact, interpretation, recommendation and placeholder content distinguishable.
- Record every approved deviation from this standard in the delivery report.
- Never claim the standard passed because the text is correct while rendering, structure or pagination remains unchecked.
