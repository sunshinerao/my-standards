# AI Build Rules v1.0

## 1. Operating Rule

When a user selects `Programme` or `Platform`, the agent must load and obey:

1. `01_GLOBAL_FOUNDATION.md`
2. Selected mode Design System
3. Selected mode Interaction System
4. This file

The selected mode is a constraint system, not an inspiration prompt.

## 2. Required Build Sequence

```text
1. Identify page type.
2. Identify content hierarchy.
3. Map content to approved components.
4. Apply mode tokens.
5. Apply responsive behavior.
6. Apply only approved interaction patterns.
7. Run the QA gate.
8. Report exceptions explicitly.
```

Do not redesign the system during implementation.

## 3. MUST

An AI agent MUST:

- Use the shared header-to-footer container alignment.
- Use the 12/6/4-column grid.
- Use mode tokens for color, spacing, radius and motion.
- Use semantic HTML before visual wrappers.
- Preserve an obvious H1 → H2 → H3 hierarchy.
- Build mobile and desktop as equal priorities.
- Respect `prefers-reduced-motion`.
- Use documentary or evidence-based imagery when real imagery is required.
- Keep essential text in HTML, not burned into images.
- Use explicit CTA labels.
- Keep data/metrics scoped by time and population/context when supplied.
- Include alt text strategy, focus state and keyboard interaction.
- Keep content readable if non-essential animation fails.
- Use conclusion-first user-facing copy.
- Separate design/development notes from public copy.
- Reuse existing components before creating new ones.
- Preserve the selected mode across all subpages.

## 4. MUST NOT

An AI agent MUST NOT:

- Invent a new visual style for each page.
- Add unapproved colors.
- Add decorative gradients unless requested.
- Add 16–32px radius to generic cards.
- Put cards inside cards.
- Use drop shadows as the default grouping device.
- Turn every section into a 3- or 4-card grid.
- Animate every section with the same fade-up effect.
- Use parallax on ordinary content.
- Use scroll-jacking.
- Hide important content behind hover.
- Use emoji as UI icons.
- Use generic “green future” stock imagery as default climate content.
- Create fake impact metrics, partner logos, quotes, speakers or event data.
- Write internal reasoning into public copy.
- use “Read more” when a specific destination label is possible.
- change header/footer alignment between page types.
- use a different button system on a subpage.
- copy third-party logos, source code, proprietary graphics or exact page layouts from reference sites.

## 5. SHOULD

An AI agent SHOULD:

- Start with real content structure before decorative treatment.
- Use one visual hero, not multiple competing hero messages.
- Use asymmetry selectively in Programme.
- Use disciplined editorial alignment in Platform.
- Alternate section density.
- Use large imagery where a story deserves focus.
- Use quiet whitespace instead of decorative separators.
- Use borders rather than shadows for institutional grouping.
- Use media credits in the content model.
- Keep navigation labels short and scalable across languages.

## 6. Content-Insufficient Behavior

When content is missing:

- Use `[Headline]`, `[Metric]`, `[Location]`, `[Date]` or clearly neutral placeholders.
- Do not manufacture factual content.
- Do not fill blank space with generic marketing copy.
- Do not add an unnecessary component solely to make the page look full.

## 7. Programme Mode Enforcement

When `Programme` is active:

- Hero media is dominant.
- The first screen contains no metric grid.
- A manifesto/meaning section follows early.
- People/place/action imagery outranks abstract graphics.
- Page rhythm includes at least one large quiet statement and one large feature story.
- Maximum two Level 3 cinematic interactions per long page.
- Repeating card sections are limited.
- CTA copy uses action verbs.
- The emotional arc is: `feel → understand → explore → act → see impact`.

## 8. Platform Mode Enforcement

When `Platform` is active:

- Institutional navigation is stable.
- Current priorities appear before generic content archives.
- Results appear on the homepage when credible metrics are available.
- Human stories follow strategic framing.
- Events use structured data fields.
- Calendar/list/map are views, not separate content silos.
- Reports and news are visually distinguishable.
- Accessibility, language and legal links are first-class footer content.
- The informational arc is: `position → priorities → results → stories → programme → resources`.

## 9. Default React / Next.js Component Names

Use these names when the project stack supports componentization.

### Shared

```text
SiteHeader
MegaMenu
SiteFooter
SectionHeader
MediaFrame
ResponsiveImage
VideoPlayer
TextLink
PrimaryButton
Metric
LanguageSwitch
SearchTrigger
```

### Programme

```text
ProgrammeHero
ManifestoStatement
JourneyRail
FeatureStory
EditorialStoryCard
PersonStory
ActionPath
ImpactBand
```

### Platform

```text
PlatformHero
InstitutionStatement
PriorityStack
MetricField
StoryRail
EventExplorer
EventCard
ReportFeature
NewsList
PartnerField
```

## 10. CSS Architecture

Preferred structure:

```text
styles/
  tokens.css
  global.css
  typography.css
  motion.css
  programme.css
  platform.css
```

Component files may use CSS modules, styled components, Tailwind or another system, but values must map to documented tokens.

Hard-coded one-off values require a comment explaining why the existing token cannot be used.

## 11. Tailwind Mapping Rule

When Tailwind is used, map tokens once in the theme. Do not scatter arbitrary values such as `mt-[73px]`, `rounded-[19px]`, or `duration-[337ms]` throughout components.

Arbitrary values are permitted only for intentional art direction and must remain rare.

## 12. Motion Implementation Rule

Preferred implementation order:

```text
CSS transition / keyframes
→ IntersectionObserver
→ Web Animations API
→ GSAP/Framer Motion only when the narrative behavior requires it
```

Do not add an animation library for hover effects or simple reveals.

## 13. Image Implementation Rule

Every image component must define:

```text
semantic purpose
alt behavior
desktop crop
mobile crop
loading priority
credit capability
```

Hero images use responsive art direction. `object-position: center` is not an acceptable universal crop strategy.

## 14. Navigation Rule

The mega menu must be one reusable component. Do not build different menu animations on different top-level items.

Required states:

```text
closed
opening
open
closing
keyboard-focus
reduced-motion
mobile
```

## 15. Accessibility Rule

Before completion, the agent must verify:

- Skip link exists.
- Focus states exist.
- Menu has `aria-expanded` and correct focus management.
- Decorative images use empty alt.
- Informative images have meaningful alt.
- Form fields have labels.
- Color contrast meets target.
- Video captions/control path exists.
- Reduced motion path exists.
- No keyboard trap remains after menu/modal close.

## 16. Automatic Visual QA Checklist

Score each item `0` or `1`.

### Shared — 10 points

1. Header/content/footer left edges align.
2. No arbitrary new colors.
3. Typography follows documented scale.
4. Section spacing follows tokens.
5. Mobile layout is not a shrunken desktop.
6. No nested-card pattern.
7. Focus/keyboard behavior is implemented.
8. Reduced motion is implemented.
9. Images follow approved ratios/art direction.
10. Page has alternating visual density.

### Programme — 10 points

1. Media-led hero.
2. Quiet manifesto section.
3. Human/place/action imagery priority.
4. Strong editorial feature story.
5. Journey/action structure is visible.
6. No dashboard-like card wall.
7. Maximum two cinematic motion moments.
8. Motion is fluid and structured.
9. Metrics are secondary to narrative.
10. Closing CTA restores emotional focus.

### Platform — 10 points

1. Stable institutional header.
2. Priorities visible before content archive.
3. Results/metrics are legible and sourced when applicable.
4. Strategic framing precedes human stories.
5. Event data is structured.
6. News/report distinction is clear.
7. Blue/neutral system remains dominant.
8. Motion is restrained and editorial.
9. Footer includes institutional utility links.
10. Information architecture supports multilingual expansion.

Pass threshold: **18/20** for the selected mode plus shared rules.

## 17. Reference Fidelity Rule

The target is **high design-language fidelity, low literal duplication**.

A successful output should reproduce:

- hierarchy
- rhythm
- interaction quality
- media dominance
- navigation behavior
- editorial pacing
- restraint

It should not reproduce:

- exact third-party layout
- logo
- trademark graphics
- copied text
- proprietary illustrations
- identical animation choreography frame-for-frame

## 18. Agent Completion Statement

At the end of an implementation task, the agent reports only:

```text
Mode: Programme | Platform
Page type: ...
QA score: .../20
Exceptions: none | [short list]
```

Do not append design reasoning unless requested.