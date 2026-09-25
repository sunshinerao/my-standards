# My Standards

**Personal Standards Repository for cross-project AI-assisted design and development**

This repository is the canonical source of truth for reusable standards used across projects. Agents must read the relevant standard files before implementation and must not rely on memory, prior chat context, or visual approximation when the repository is available.

Current published module:

- **Web Standards v1.0**
  - **Programme mode** — programme, initiative, youth, exploration, action and story-led websites.
  - **Platform mode** — institution, climate week, knowledge platform, event network and public-facing platform websites.

Word/document standards are **not yet published in this repository**.

---

## 1. Core operating rule

This repository defines the standards. A project defines only:

1. which standard mode it uses;
2. which repository commit/version it is pinned to;
3. which explicitly approved project-specific exceptions apply.

Agents must not redesign the standard during implementation.

When this repository and a project-specific instruction conflict, precedence is:

1. Explicit instruction in the current task;
2. Approved project-specific exception;
3. Selected mode Design System;
4. Selected mode Interaction System;
5. Global Foundation;
6. Agent defaults.

---

## 2. Web modes

### Programme

Use for programme-led, initiative-led and story-led experiences.

Design DNA:

- cinematic;
- human and place-led;
- action-led;
- editorial;
- optimistic but restrained.

Primary references:

- The Earthshot Prize — visual language and homepage expression;
- IDEO.org — editorial project presentation;
- TED Countdown — story, video and community pathways.

Activation phrase:

```text
Use Website Design System v1.0 — Programme mode.
```

### Platform

Use for institutional, convening, knowledge and event-platform experiences.

Design DNA:

- institutional;
- editorial;
- global;
- calm;
- structured;
- information-rich without visual clutter.

Primary references:

- United Nations web language — institutional clarity;
- The Rockefeller Foundation — homepage narrative and interaction quality;
- Climate Week NYC — event discovery;
- London Climate Action Week — distributed programme ecosystem.

Activation phrase:

```text
Use Website Design System v1.0 — Platform mode.
```

---

## 3. Required Agent startup instructions

For a **Programme** project, give the Agent this instruction:

```text
Use Website Design System v1.0 — Programme mode.

Before making any UI/UX, frontend, layout, typography, image, animation,
navigation or component decision:

1. Read the root README.md and AGENTS.md in sunshinerao/my-standards.
2. Read:
   - web/01_GLOBAL_FOUNDATION.md
   - web/programme/DESIGN_SYSTEM.md
   - web/programme/INTERACTION_SYSTEM.md
   - web/AI_BUILD_RULES.md
   - web/REFERENCE_REGISTRY.md
3. Treat these files as normative constraints, not inspiration.
4. Do not introduce new visual patterns, colors, spacing systems, radii,
   card styles, interaction behaviors or motion patterns unless explicitly approved.
5. Reuse approved components before creating new ones.
6. Preserve the project’s existing technical stack unless explicitly instructed otherwise.
7. Before delivery, run the Website Design System QA checklist in web/AI_BUILD_RULES.md.
8. If the selected-mode score is below 18/20, revise before delivery.
9. Report only:
   Mode
   Page type
   QA score
   Exceptions
10. Do not write design reasoning into public-facing copy unless asked.
```

For a **Platform** project, use the same instruction but replace the mode and paths:

```text
Use Website Design System v1.0 — Platform mode.

Before making any UI/UX, frontend, layout, typography, image, animation,
navigation or component decision:

1. Read the root README.md and AGENTS.md in sunshinerao/my-standards.
2. Read:
   - web/01_GLOBAL_FOUNDATION.md
   - web/platform/DESIGN_SYSTEM.md
   - web/platform/INTERACTION_SYSTEM.md
   - web/AI_BUILD_RULES.md
   - web/REFERENCE_REGISTRY.md
3. Treat these files as normative constraints, not inspiration.
4. Do not introduce new visual patterns, colors, spacing systems, radii,
   card styles, interaction behaviors or motion patterns unless explicitly approved.
5. Reuse approved components before creating new ones.
6. Preserve the project’s existing technical stack unless explicitly instructed otherwise.
7. Before delivery, run the Website Design System QA checklist in web/AI_BUILD_RULES.md.
8. If the selected-mode score is below 18/20, revise before delivery.
9. Report only:
   Mode
   Page type
   QA score
   Exceptions
10. Do not write design reasoning into public-facing copy unless asked.
```

---

## 4. Recommended project integration

For production projects, pin this repository to a specific commit instead of silently following the latest main branch.

Recommended structure:

```text
project/
├── AGENTS.md
├── standards.lock.md
└── .standards/
    └── my-standards/   # Git submodule or pinned snapshot
```

Recommended submodule command:

```bash
git submodule add https://github.com/sunshinerao/my-standards.git .standards/my-standards
```

The project’s own `AGENTS.md` should state:

```text
Design authority: sunshinerao/my-standards
Mode: Programme | Platform
Pinned commit: <FULL_COMMIT_SHA>

The standards repository is authoritative for visual and interaction decisions.
Project-specific deviations require explicit approval and must be documented.
```

---

## 5. Repository structure

```text
my-standards/
├── README.md
├── AGENTS.md
├── VERSION
└── web/
    ├── README.md
    ├── 01_GLOBAL_FOUNDATION.md
    ├── AI_BUILD_RULES.md
    ├── REFERENCE_REGISTRY.md
    ├── VALIDATION_REPORT.md
    ├── programme/
    │   ├── DESIGN_SYSTEM.md
    │   └── INTERACTION_SYSTEM.md
    └── platform/
        ├── DESIGN_SYSTEM.md
        └── INTERACTION_SYSTEM.md
```

---

## 6. Mandatory non-drift rule

The following are prohibited unless explicitly approved:

- arbitrary new colors;
- arbitrary spacing values where tokens exist;
- generic large rounded SaaS cards;
- cards inside cards;
- default drop-shadow grouping;
- decorative gradients outside the standard;
- repeating 3/4-card walls across the whole page;
- animating every section with the same fade-up;
- generic parallax;
- scroll-jacking;
- hover-only access to important content;
- generic “green future” sustainability stock imagery;
- fake metrics, logos, quotes, speakers or event information;
- different header/footer alignment on different pages;
- a new navigation animation for each menu;
- copying reference-site source code, logos, exact layouts or proprietary graphics.

---

## 7. Versioning

Current repository baseline:

```text
Repository: my-standards
Web Design System: v1.0
Modes: Programme / Platform
```

A project should record the exact commit SHA it uses. Updating the standards repository does not automatically approve a production project migration.

---

## 8. References and copying boundary

Reference sites define design principles and quality targets only.

The system may reproduce:

- hierarchy;
- rhythm;
- media dominance;
- editorial pacing;
- interaction quality;
- navigation behavior;
- restraint.

The system must not reproduce:

- exact third-party layouts;
- logos or wordmarks;
- copyrighted copy;
- proprietary illustrations;
- third-party photographs;
- source code;
- frame-for-frame proprietary animations.

---

## 9. Status

| Module | Status |
|---|---|
| Web / Global Foundation | Published v1.0 |
| Web / Programme | Published v1.0 |
| Web / Platform | Published v1.0 |
| Web / AI Build Rules | Published v1.0 |
| Word / Documents | Not yet published |
| Presentation standards | Not yet published |
| Other standards | Not yet published |

This repository should grow by adding approved standards, not by mixing project-specific implementation code into the standards layer.
