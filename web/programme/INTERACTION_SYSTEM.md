# Programme Interaction System v1.0

## 1. Motion Character

**Fluid, structured, optimistic, restrained.** Motion suggests expansion, connection, discovery and forward movement. It never becomes a showreel.

The primary reference language is The Earthshot Prize’s motion-led identity: fluid but structured transitions, strong typography, visual focus on solutions and people. Cinematic behavior is limited to a small number of narrative moments.

## 2. Motion Tokens

```css
:root[data-mode="programme"] {
  --motion-instant: 120ms;
  --motion-fast: 180ms;
  --motion-ui: 260ms;
  --motion-section: 520ms;
  --motion-story: 780ms;
  --motion-cinematic: 1100ms;

  --ease-standard: cubic-bezier(.2,.7,.2,1);
  --ease-out: cubic-bezier(.16,1,.3,1);
  --ease-in-out: cubic-bezier(.65,0,.35,1);
}
```

## 3. Motion Levels

### Level 0 — Static

Never animate by default:

- Body copy.
- Legal text.
- Form labels.
- Long reports.
- Accessibility controls.
- Essential status text.

### Level 1 — Functional

Use 120–260ms:

- Button hover.
- Link underline.
- Accordion.
- Filter.
- Navigation icon.
- Form state.

### Level 2 — Editorial

Use 360–780ms:

- Section image reveal.
- Headline entrance.
- Story-card media zoom.
- Metric entrance.
- Chapter marker transition.

### Level 3 — Cinematic

Use at most **two** moments per long page:

- Hero media transition.
- Journey sequence.
- Film/story transition.
- Controlled pinned storytelling.

## 4. Header States

### Hero State

```text
background: transparent
logo/text: chosen for media contrast
height: 84–96px desktop / 68–76px mobile
```

### Scrolled State

Trigger: 48–96px page scroll or leaving hero intro zone.

```text
background: rgba(surface, .96)
text: ink
border-bottom: hairline
height: 68–76px desktop / 60–68px mobile
backdrop blur: optional 8–12px
transition: 260–360ms
```

Header geometry changes once. Repeated hide/show on every small scroll is not default Programme behavior.

## 5. Programme Menu

Desktop may use a full-width panel for deep information architecture.

Open sequence:

```text
0ms      background scrim begins
20ms     menu panel clip-path expands downward
100ms    primary links rise 12–18px and fade in
160ms    secondary links follow with 30–45ms stagger
220ms    featured image/story appears
```

Total: 480–620ms.

Close sequence: 300–420ms, reverse hierarchy, no long stagger.

Mandatory behavior:

- Body scroll lock.
- `Esc` closes.
- Focus trap.
- Opening trigger uses `aria-expanded`.
- Focus returns to trigger.
- Menu is usable without hover.

## 6. Hero Motion

Default image hero:

```text
media scale: 1.025 → 1.0 over 1100ms on load
headline: y 28px → 0 + opacity 0 → 1 over 700ms
CTA: y 12px → 0 + opacity 0 → 1 after headline
```

Default video hero:

- Video itself does not animate through CSS beyond a subtle initial opacity.
- No continuous artificial zoom.
- Text enters independently.

On scroll:

- Hero media may translate/scale by no more than 4% over the hero range.
- Hero text may fade to 0.7 as it exits.
- Avoid dramatic parallax that disconnects text from image.

## 7. Text Reveal

Approved for manifesto/display statements only.

Pattern A — line reveal:

```text
mask overflow hidden
line y: 105% → 0
stagger: 70–110ms
```

Pattern B — opacity emphasis:

```text
paragraph remains visible at 0.25–0.35 opacity
active phrase transitions to 1.0 based on scroll progress
```

Pattern B is limited to one section per page.

## 8. Image Reveal

Default editorial reveal:

```text
container overflow hidden
image scale: 1.04 → 1
mask/clip: inset(0 0 100% 0) → inset(0)
duration: 620–780ms
```

Use only when image first enters. Do not repeat on reverse scroll.

## 9. Card Hover

Desktop pointer devices:

```text
image scale: 1 → 1.025 / 320ms
link arrow x: 0 → 5px / 180ms
underline: 0 → 100%
```

Card container stays fixed. No lift shadow.

Touch devices: no hover-dependent meaning.

## 10. Journey Rail

Desktop behavior:

- May use horizontal progression driven by explicit controls or bounded scroll mapping.
- The section must expose a vertical semantic document order.
- Current stage is visually emphasized through scale/opacity, not hidden accessibility content.
- User can reach all stages via keyboard.

Mobile behavior:

- Vertical stack by default.
- No scroll-jacking.
- No forced snapping.

## 11. Pinned Storytelling

Allowed only when:

- The content sequence materially benefits from visual continuity.
- The pinned region is ≤2 viewport heights of controlled progression.
- Mobile has a non-pinned version.
- Reduced-motion has a non-pinned version.

Do not pin ordinary text sections.

## 12. Metrics

Count-up is optional.

If used:

- Trigger once at 30–50% visibility.
- Duration 700–1000ms.
- Final value is available immediately to assistive technology.
- Decimal and unit formatting do not shift layout.

## 13. Page Transitions

Default: native navigation. SPA transitions are optional.

If enabled:

```text
exit: 180–240ms opacity
enter: 320–480ms opacity + y 8–12px
```

Never delay route navigation for an ornamental transition.

## 14. Reduced Motion

```css
@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after {
    scroll-behavior: auto !important;
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
  }
}
```

Pinned, parallax and count-up behaviors become static.

## 15. Motion Budget

Per viewport, only one element group may use Level 2 or Level 3 motion at a time.

A page fails when:

- Every section fades up.
- Multiple objects continuously float.
- Text tracks cursor movement.
- Scroll position controls decorative 3D motion without content value.
- Motion delays reading or navigation.