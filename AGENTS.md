# AGENTS.md

This repository contains normative reusable standards.

## 1. Agent entry rule

Before implementing any website UI/UX or frontend work that cites this repository, the Agent MUST:

1. identify the selected mode: `Programme` or `Platform`;
2. read `README.md`;
3. read `web/01_GLOBAL_FOUNDATION.md`;
4. read the selected mode's `DESIGN_SYSTEM.md`;
5. read the selected mode's `INTERACTION_SYSTEM.md`;
6. read `web/AI_BUILD_RULES.md`;
7. read `web/REFERENCE_REGISTRY.md`;
8. run the QA checklist before delivery.

The standards are constraints, not a moodboard.

## 2. Fixed activation commands

### Programme

```text
Use Website Design System v1.0 — Programme mode.
Read and obey sunshinerao/my-standards before implementation.
```

Required files:

```text
README.md
AGENTS.md
web/01_GLOBAL_FOUNDATION.md
web/programme/DESIGN_SYSTEM.md
web/programme/INTERACTION_SYSTEM.md
web/AI_BUILD_RULES.md
web/REFERENCE_REGISTRY.md
```

### Platform

```text
Use Website Design System v1.0 — Platform mode.
Read and obey sunshinerao/my-standards before implementation.
```

Required files:

```text
README.md
AGENTS.md
web/01_GLOBAL_FOUNDATION.md
web/platform/DESIGN_SYSTEM.md
web/platform/INTERACTION_SYSTEM.md
web/AI_BUILD_RULES.md
web/REFERENCE_REGISTRY.md
```

## 3. Precedence

Within authorized project scope:

1. Current explicit user instruction.
2. Explicit approved project exception.
3. Selected mode Design System.
4. Selected mode Interaction System.
5. Global Foundation.
6. Agent defaults.

Reference sites never override repository standards.

## 4. Build behavior

The Agent MUST:

- preserve header-to-footer alignment;
- use documented tokens;
- preserve mode-specific typography, image and motion systems;
- use existing components before inventing new ones;
- implement mobile and desktop as equal priorities;
- implement keyboard and reduced-motion behavior;
- keep essential content in semantic HTML;
- keep public-facing copy conclusion-first;
- distinguish factual content from placeholders;
- report exceptions rather than silently changing the standard.

The Agent MUST NOT:

- redesign the system during implementation;
- add arbitrary colors, radii, shadows or gradients;
- create card walls by default;
- use nested cards;
- animate every section;
- use scroll-jacking;
- hide essential content behind hover;
- manufacture data, partners, speakers, quotes or metrics;
- copy proprietary reference-site assets, layouts, source code or exact animation choreography.

## 5. Completion gate

Every website implementation must be scored using the 20-point selected-mode checklist in `web/AI_BUILD_RULES.md`.

Minimum passing score:

```text
18 / 20
```

Blocking accessibility, broken-link or content-integrity failures must be fixed even if the numeric score passes.

Completion statement:

```text
Mode: Programme | Platform
Page type: ...
QA score: .../20
Exceptions: none | [short list]
```

Do not append internal design reasoning unless specifically requested.

## 6. Version discipline

Production projects should pin this repository to a full commit SHA.

Do not assume that `main` is the approved production version for an existing project.

A project-specific exception belongs in that project, not in this repository unless it has been approved as a reusable standard.
