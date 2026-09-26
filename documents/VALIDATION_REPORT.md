# Word v1.1 Calibration Validation

Date: 2026-09-26

## Evidence set

| Item | SHA-256 |
|---|---|
| User-edited `Word_Standard_Test_v2_checked.docx` | `60c0755cab0dd967614d02b584b2509dc695e197d22bf1f564a6fa1022b8b10d` |
| Prior `ChatGPT_Word文档全局格式规范_V1.0.docx` | `efe81ba060293fa3d22ae66727afc517216613c4e968a179978faf19b6f57af4` |

The source files were inspected read-only and were not committed to this repository.

## Requested change 1: italic explanatory notes

The v1.0 prose standard specified `10.5 pt` italic notes. The user approved a new exact value of `9 pt`.

OOXML inspection of the user-edited test document found four italic explanatory/boundary-note paragraphs:

- three paragraphs use `w:sz=18`, which equals `9 pt` for their actual Chinese and Latin content; those runs retain an unused `w:szCs=20` complex-script value, so v1.1 requires `w:szCs=18` when that property is present;
- one paragraph beginning `说明：复盘结论应与实际证据相互对应` still uses `w:sz=21`, which equals `10.5 pt`.

Result: **the intended change is confirmed, but the supplied file is internally inconsistent**. The normative v1.1 rule is therefore `9 pt` for every explanatory-note run, and the QA checklist requires a full-document check rather than sampling.

## Requested change 2: bullet alignment

The v1.0 prose standard specified:

- left indent `0.80 cm`;
- hanging indent `0.35 cm`;
- implied bullet position `0.45 cm` from the content-area left edge.

All three level-0 bullet definitions actually used by the edited test document resolve to:

```xml
<w:numFmt w:val="bullet"/>
<w:lvlJc w:val="left"/>
<w:ind w:left="360" w:hanging="360"/>
```

This means:

- text indent `360 twips = 0.635 cm`;
- hanging indent `360 twips = 0.635 cm`;
- bullet position `0 cm`, aligned to the content-area left edge.

Result: **confirmed consistently across all 14 bullet paragraphs**. The v1.1 token file records both human units and OOXML units so future builders do not reinterpret the geometry.

## Other retained calibration facts

- The DOCX ZIP package passed integrity testing.
- The document has one A4 portrait section with a different first page.
- Body-region paragraphs use `w:line=360` and `lineRule=auto`, representing `1.5×` line spacing.
- The tested role spacing uses equal before and after values; final paragraphs in groups use `0/0`.
- The document rendered to six pages without clipping or overlapping.
- The QA renderer did not have the required Chinese font, so Chinese glyphs appeared as missing-glyph boxes. Layout inspection passed, but final Chinese font fidelity could not be confirmed in that environment.

## Acceptance decision

The two requested rules are now published as normative v1.1 values. The source document itself is not labeled fully conforming because one italic note remains at `10.5 pt` and the render environment could not prove final Chinese font fidelity.
