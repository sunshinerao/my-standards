# Global Foundation v1.0

## 1. Core Principle

**One alignment system runs from header to footer.** Major sections share the same outer grid. Full-bleed media may escape the container; its internal text returns to the same grid.

The system prioritizes clarity, editorial hierarchy, authentic photography, accessibility, performance and long-term modularity.

## 2. Layout Tokens

```css
:root {
  --page-max: 1440px;
  --content-max: 1320px;
  --text-max: 760px;
  --measure: 68ch;

  --gutter-mobile: 20px;
  --gutter-tablet: 32px;
  --gutter-desktop: 48px;
  --gutter-wide: 64px;

  --space-1: 4px;
  --space-2: 8px;
  --space-3: 12px;
  --space-4: 16px;
  --space-5: 24px;
  --space-6: 32px;
  --space-7: 48px;
  --space-8: 64px;
  --space-9: 96px;
  --space-10: 128px;
  --space-11: 160px;
  --space-12: 200px;

  --border-hairline: 1px;
  --focus-ring: 3px;
}
```

### Grid

- Desktop ≥1280: **12 columns**, 24px minimum gutter.
- Tablet 768–1279: **6 columns**, 20–24px gutter.
- Mobile <768: **4 columns**, 16px gutter.
- Text blocks do not exceed 68ch unless they are display statements.
- Body copy uses 45–75 characters per line as the target readable range.
- Header, content and footer anchors use one shared container function.

Recommended container:

```css
.container {
  width: min(var(--content-max), calc(100vw - 2 * var(--gutter-desktop)));
  margin-inline: auto;
}
```

Use responsive gutters through `clamp()` or breakpoint tokens.

## 3. Breakpoints

```text
xs:  360
sm:  480
md:  768
tb:  1024
lg:  1280
xl:  1600
```

Breakpoints exist for layout change, not device branding.

## 4. Section Rhythm

A page must alternate density. Five consecutive equal-height sections are prohibited.

Approved rhythm pattern:

```text
IMMERSIVE / QUIET / EDITORIAL / DENSE / IMMERSIVE / DATA / QUIET CTA
```

Default section spacing:

- Mobile: 72–96px vertical.
- Tablet: 88–120px vertical.
- Desktop: 112–160px vertical.
- Hero-to-first-section transition may use 160–220px when the design calls for a deliberate pause.

## 5. Typography Rules

- Use a maximum of **two type families** per site.
- Use a maximum of **four functional weights**.
- Display typography uses optical sizing and tight tracking only where legibility remains strong.
- Body typography never goes below 16px on mobile or desktop.
- Small metadata never goes below 12px.
- Long-form line-height: 1.5–1.7.
- Display line-height: 0.92–1.08.
- Headings follow semantic hierarchy. Visual size must not replace HTML heading order.
- Chinese and English typography must preserve equivalent visual hierarchy, not identical character count.

## 6. Color Rules

- Every mode defines its own palette.
- Body text must meet WCAG AA contrast.
- Color must never be the only carrier of meaning.
- A page uses one dominant neutral field plus no more than two active accent colors at the same time.
- Decorative gradients are prohibited unless explicitly defined by the selected mode.

## 7. Image Rules

Every image must have one job: **establish place, reveal people, show action, document evidence, or explain a system.**

Standard ratios:

```text
Hero desktop        16:9 to 2:1
Hero mobile         4:5
Feature editorial   3:2
Card landscape      4:3
Portrait            3:4
Cinematic strip     21:9
Square data/story   1:1
```

Image cropping preserves faces, hands, critical objects and architecture. AI-generated stock-like sustainability clichés are prohibited by default.

## 8. Video Rules

- Autoplay video must be muted, inline, loop only when the loop is editorially meaningful.
- A visible pause control is mandatory when motion persists beyond 5 seconds.
- Poster image is mandatory.
- Captions are mandatory for spoken content.
- Hero video must not contain essential text burned into the image.
- Video is disabled or simplified under `prefers-reduced-motion`.

## 9. Icon Rules

- Use one icon family only.
- Line icons use consistent stroke width.
- Icons never substitute for essential labels.
- Emoji are prohibited in production UI.

## 10. Radius, Borders and Shadows

- Large rounded cards are not a default design language.
- Radius exists only when the mode explicitly permits it.
- Hairline borders are preferred to drop shadows.
- Shadows are reserved for overlays, menus and floating controls.
- Nested cards are prohibited.

## 11. Accessibility Baseline

Target: **WCAG 2.2 AA**.

Mandatory:

- Skip-to-content link.
- Keyboard-operable navigation and sub-navigation.
- Visible focus state.
- Semantic landmarks: `header`, `nav`, `main`, `footer`.
- Valid heading order.
- Alt text policy.
- Form labels remain visible.
- Minimum pointer target: 44×44px.
- Motion respects `prefers-reduced-motion`.
- Carousel, video and timed content provide user control.
- Modal and mega menu trap focus while open and restore focus on close.
- Body content remains understandable when CSS animation and non-essential JS fail.

## 12. Multilingual Baseline

- Navigation labels are designed for 30–60% expansion.
- Chinese and English may wrap differently; layouts must not rely on fixed character counts.
- Language switching never changes information architecture.
- Dates and times use locale-aware formatting.
- Mixed CJK/Latin text uses tested fallback fonts.

## 13. Performance Baseline

Targets for production landing pages:

```text
LCP ≤ 2.5s
CLS ≤ 0.1
INP ≤ 200ms
Initial JS target ≤ 180KB gzip when feasible
Hero media uses responsive sources
Images default to AVIF/WebP with fallback
Below-fold media lazy loads
```

Motion must use transform/opacity where possible. Layout-thrashing scroll handlers are prohibited.

## 14. Content Rules

- One section = one primary idea.
- One screen = one dominant visual hierarchy.
- Homepages use conclusion-first copy.
- Internal reasoning, design rationale and production notes never appear in user-facing copy.
- Generic phrases such as “Together for a better future” are prohibited unless explicitly supplied by the content owner.
- Metrics must include scope and time period when the context is not self-evident.

## 15. Navigation Baseline

- Primary navigation: target 4–6 items.
- Utility actions are visually separated from primary navigation.
- The active page is identifiable.
- Deep sites use mega menus; shallow sites use direct links.
- Search is a utility, not a primary navigation item unless content volume requires it.

## 16. QA Gate

A page cannot be considered complete until it passes:

1. Alignment test.
2. Mobile test at 390px.
3. Tablet test at 768/1024px.
4. Desktop test at 1440px.
5. Keyboard navigation test.
6. Reduced-motion test.
7. Image crop test.
8. Copy hierarchy test.
9. Contrast test.
10. Link and CTA test.