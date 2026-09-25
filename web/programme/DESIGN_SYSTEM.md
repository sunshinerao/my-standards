# Programme Design System v1.0

## 1. Identity

**Programme = cinematic optimism + human evidence + place + action.**

The visual system is quiet enough for real stories to dominate and bold enough to create emotional momentum. It avoids NGO-template aesthetics, corporate ESG clichés and decorative interface noise.

Primary reference role:

- **The Earthshot Prize:** visual DNA, optimistic environmental storytelling, hero behavior, spacious layout, bold grotesk typography, scalable modular system.
- **IDEO.org:** editorial project presentation, asymmetric work grid, impact framing, questions as content.
- **TED Countdown:** video-first climate storytelling, human voice, solution framing and community pathways.

## 2. Brand Character

```text
Optimistic, not naive.
Prestigious, not ceremonial.
Young, not childish.
Cinematic, not theatrical.
Global, not generic.
Action-led, not campaign-slogan-led.
```

## 3. Color System

The palette is nature-derived but not “green NGO”. White space remains dominant.

```css
:root[data-mode="programme"] {
  --p-bg: #F5F6F1;
  --p-surface: #FFFFFF;
  --p-ink: #10201B;
  --p-ink-soft: #42514B;
  --p-line: #CBD3CD;

  --p-forest: #174C3B;
  --p-moss: #6C8E54;
  --p-lime: #C7E86B;
  --p-water: #6DB7C8;
  --p-sky: #CFE8EC;
  --p-sand: #E7DFC9;
  --p-sun: #E8C35A;
}
```

Rules:

- Background is off-white or photographic.
- `--p-forest` is the dominant identity color.
- `--p-lime`, `--p-water`, `--p-sun` are thematic accents, not simultaneous decoration.
- Only one thematic accent is active in a content section unless a multi-theme index explicitly requires several.
- Pure black is avoided in large fields; `--p-ink` is preferred.
- Gradients are not part of the base system. A photographic overlay may use a single transparent ink wash for legibility.

## 4. Typography

### Preferred

- **Primary:** GT America, if a valid license exists.
- **Open-source fallback:** Inter Tight.
- **System fallback:** Inter, Arial, Helvetica, sans-serif.
- **Chinese fallback:** Noto Sans SC / Source Han Sans SC / PingFang SC.

The type system is sans-serif dominant. A separate serif is not required.

### Scale

```css
--p-display-xl: clamp(4.25rem, 8.4vw, 8.75rem);
--p-display-lg: clamp(3.25rem, 6vw, 6.5rem);
--p-h1: clamp(3rem, 5vw, 5.5rem);
--p-h2: clamp(2.25rem, 3.6vw, 4rem);
--p-h3: clamp(1.5rem, 2.2vw, 2.5rem);
--p-body-lg: clamp(1.2rem, 1.5vw, 1.5rem);
--p-body: 1rem;
--p-meta: .75rem;
```

Rules:

- Display headings: 600–700 weight, tracking -0.02em to -0.04em.
- Body: 400–500 weight.
- Metadata: uppercase is permitted; letter spacing +0.06em to +0.12em.
- Headlines may occupy 7–10 columns on desktop. Body copy usually occupies 4–6 columns.
- Large statements use short lines. Forced line breaks must be intentional.

## 5. Layout Grammar

Programme pages use **large visual fields + decisive whitespace + irregular editorial composition**.

Approved section forms:

1. Full-bleed media with text overlay.
2. Full-width statement on quiet background.
3. 7/5 image-text split.
4. 5/7 text-image split.
5. 8/4 feature story.
6. 3-up editorial cards.
7. Horizontal journey rail.
8. Full-width metric field.
9. Portrait/story grid.
10. Minimal closing CTA.

Prohibited default:

- Repeating 4-card grids down the entire page.
- Icon-over-title-over-copy feature boxes.
- Dashboard-style tiles.
- Rounded SaaS cards.
- Color blocks nested inside color blocks.

## 6. Homepage Anatomy

The default Programme homepage follows this order:

### 01 — Hero / Emotional Entry

- 85–100svh desktop.
- 78–92svh mobile.
- Dominant media: full-bleed documentary image or short loop video.
- Content: eyebrow + one large statement + one primary CTA.
- Maximum 18 English words or equivalent visual density in the main statement.
- No metric cards, partner logos or explanatory paragraphs in the hero.

### 02 — Manifesto / Why This Matters

- Quiet field.
- 1–3 large sentences.
- Text reveal may be used.
- Purpose: shift from emotion to meaning.

### 03 — Journey / Chapters / Places

- 3–6 stages.
- Can be horizontal on desktop with vertical accessible fallback on mobile.
- Each stage has: number, place/theme, one verb, one-line context.
- No mini-card chrome.

### 04 — Featured Story

- Large image or film.
- One primary story only.
- Caption and CTA sit within the shared grid.

### 05 — Story / Heritage / Solution Index

- 2–3 columns desktop, 1 column mobile.
- Images dominate card height.
- Titles are questions or strong statements when appropriate.

### 06 — People

- Documentary portraiture.
- Person + role + one meaningful line.
- Avoid “wall of headshots”.

### 07 — Action Pathways

- 3–6 verbs or actions.
- Each action maps to a real next step.
- No abstract “Learn more” CTA when a more specific action is possible.

### 08 — Impact

- Large numerals.
- 3–5 metrics maximum.
- Metrics include time/scope labels.

### 09 — Closing Statement

- One memorable proposition.
- One primary CTA and optional secondary text link.
- Strong visual pause before footer.

## 7. Image System

### Subject Priority

```text
1. People doing something real
2. Place and landscape with human context
3. Heritage / built environment / ecosystems
4. Evidence of action or transformation
5. Scientific / technical detail
```

### Photography Direction

- Documentary, observed, tactile.
- Natural light preferred.
- Human scale remains visible.
- Imperfection is acceptable; staged corporate polish is not.
- Wide establishing image + close human detail should alternate through long pages.
- Faces are not required in every image.

### Prohibited Image Tropes

- Hands holding a seedling on white background.
- Generic wind-turbine sunset as default climate imagery.
- Globe in hands.
- Corporate handshake.
- Anonymous boardroom as “action”.
- Overly synthetic AI environmental fantasy.

## 8. Core Components

### `ProgrammeHero`

Fields:

```text
eyebrow
headline
supporting_line? (max 2 lines)
primary_cta
media_type: image | video
media
credit?
```

Behavior: defined in Interaction System.

### `ManifestoStatement`

- Max width: 10 columns.
- 40–110 characters per statement line group.
- No card container.

### `JourneyRail`

Fields:

```text
index
place_or_theme
action_verb
description
status? 
media?
```

### `FeatureStory`

- 8/4 or full-width composition.
- Image/video first.
- Metadata above title.
- CTA is explicit: `Explore Liangzhu`, `Watch the Film`, `Read the Field Note`.

### `EditorialStoryCard`

- Image ratio: 4:3 or 3:2.
- No shadow.
- Radius: 0–4px.
- Entire card may be clickable if semantics remain clear.
- Hover affects image and CTA only; container does not float upward.

### `PersonStory`

- Portrait ratio: 3:4.
- Role is secondary.
- Quote/point of view may replace biography.

### `ImpactBand`

- 3–5 metrics.
- Large figures align on one baseline on desktop.
- Values never animate from misleading zero when the metric is already known to the user; count-up is optional and decorative.

### `ActionPath`

- Action verb is the primary label.
- One sentence explains the outcome.
- Arrow or line motion may indicate direction.

### `ProgrammeFooter`

- Large closing wordmark or identity area.
- 2–4 navigation groups.
- Newsletter optional.
- Legal and credits remain visually quiet.

## 9. Buttons and Links

Primary button:

```text
height: 48–54px
radius: 999px OR 2px, chosen once per site and never mixed
padding-inline: 22–28px
```

Programme default: **pill may be used only for primary action controls**. Cards and media do not inherit pill radius.

Text links use arrow motion or underline reveal. `Read more` alone is discouraged.

## 10. Page Types

Approved templates:

- Homepage
- Programme Overview
- Place / City Chapter
- Heritage / Field Story
- Person / Mentor / Steward Profile
- Action Detail
- Event / Gathering
- Film / Media Story
- Impact / Results
- Journal / Insight
- Join / Apply

Every page type must start from existing components. New components require a documented reason.

## 11. Mobile Rules

- Story order remains narrative; desktop asymmetry must collapse without changing meaning.
- Horizontal journey becomes vertical snap-free sequence by default.
- Hero text does not exceed ~45% of the visual height.
- Sticky/pinned storytelling is removed when it creates scroll traps.
- Media may become taller on mobile (`4:5`) rather than simply cropping a desktop banner.

## 12. Signature Test

A Programme page is on-system when:

- A human or place is visually dominant.
- The first screen creates emotional direction without over-explaining.
- White/quiet space is visible between major stories.
- Typography is bold but not decorative.
- Cards do not dominate the page grammar.
- Motion amplifies narrative rather than UI novelty.
- The page can be understood with motion disabled.