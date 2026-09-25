# Platform Interaction System v1.0

## 1. Motion Character

**Editorial precision + institutional restraint + deliberate transitions.**

Motion guides hierarchy, reveals media and supports complex navigation. It does not compete with content.

The reference feeling is Rockefeller-style polished editorial motion combined with UN-style predictability and accessible behavior.

## 2. Motion Tokens

```css
:root[data-mode="platform"] {
  --motion-instant: 100ms;
  --motion-fast: 160ms;
  --motion-ui: 240ms;
  --motion-panel: 420ms;
  --motion-section: 560ms;
  --motion-story: 760ms;

  --ease-standard: cubic-bezier(.2,.7,.2,1);
  --ease-out: cubic-bezier(.16,1,.3,1);
  --ease-panel: cubic-bezier(.77,0,.18,1);
}
```

## 3. Header States

### Default Light Hero

```text
background: surface
text: ink
border-bottom: hairline
height: 82–92px desktop
```

### Media Hero Variant

```text
background: transparent
text: selected for contrast
```

At 64–96px scroll:

```text
background → surface 96–100%
text → ink
height → 68–76px
hairline appears
transition 260–340ms
```

The header remains stable. Auto-hide-on-scroll is not default.

## 4. Desktop Mega Menu

This is a signature interaction.

### Layout

```text
left: primary navigation group / current section
center: secondary links
right: one featured story, report or image
bottom: optional utility row
```

The menu occupies approximately 55–80svh depending on content depth.

### Open Sequence

```text
0ms       scrim opacity 0 → .28
0ms       panel clip-path inset(0 0 100% 0) → inset(0)
70ms      main heading y 16px → 0, opacity 0 → 1
120ms     primary links enter with 28–40ms stagger
180ms     secondary columns enter
230ms     feature media clip-reveals
```

Total perceived opening: **480–560ms**.

### Close Sequence

- 280–360ms.
- Media and text fade first.
- Panel closes upward.
- Scrim finishes last.

### Rules

- One menu panel at a time.
- `Esc` closes.
- Focus trapped.
- Current top-level item is visually indicated.
- Menu may be opened by click; hover can preview but cannot be the only input.
- Background page is inert while open.
- Mobile uses full-screen navigation without featured media by default.

## 5. Link and Button Motion

Text link:

```text
underline width 0 → 100% / 180ms
arrow x 0 → 4px / 160ms
```

Filled button:

```text
background tone shift: 160ms
text remains stable
no scale bounce
```

No magnetic buttons by default.

## 6. Hero Motion

Hero entrance:

```text
headline opacity 0 → 1
headline y 18px → 0
supporting line follows by 80ms
CTA follows by 120ms
media opacity 0 → 1 over 600–800ms
```

No continuous floating graphics.

## 7. Priority Stack Interaction

Desktop variant may use sticky media.

Behavior:

- Text priorities remain in normal document flow.
- Media region can remain sticky within the section.
- When a priority crosses 45–55% viewport height, its media updates.
- Media transition: opacity + clip, 420–600ms.
- Text never becomes unreadable because it is “inactive”.

Mobile:

- Each priority carries its own media.
- No sticky behavior by default.

## 8. Image / Video Reveal

Default:

```text
clip reveal from bottom or left
opacity 0.6 → 1
image scale 1.015 → 1
520–720ms
```

Do not reveal every thumbnail independently. Group repeated lists.

## 9. Metric Motion

Count-up is permitted when the metric block is editorial and the final values are present in accessible text.

Rules:

- Trigger once.
- 650–900ms.
- Number width is stabilized.
- No roulette, odometer or slot-machine effects.

## 10. News and List Interaction

Rows are interactive through subtle line/arrow behavior.

On hover:

```text
row background: neutral tint OR none
headline underline/reveal
arrow x 0 → 4px
```

The row does not lift or cast a shadow.

## 11. Event Explorer Interaction

### Filter Drawer

Desktop: inline panel or side panel.  
Mobile: bottom sheet or full-screen filter view.

Requirements:

- Applied filter count is visible.
- Clear-all is available.
- Filter state persists in URL where feasible.
- Results count updates without disorienting reflow.
- Keyboard focus moves to results summary after filter apply when appropriate.

### View Switch

```text
List | Calendar | Map
```

- The same underlying events are used.
- View selection is persistent within the session.
- Map markers expose event title/date through accessible list linkage.

## 12. Map Behavior

- Map is an exploration layer, not the sole source of event information.
- Selected marker synchronizes with a visible event card/list item.
- Clustering is used in dense urban areas.
- Hover is optional; click/tap and keyboard selection are mandatory.
- The map does not auto-pan aggressively on every filter change.

## 13. Editorial Story Rail

Desktop:

- 2.2–3 cards visible when horizontal.
- Drag is optional; explicit previous/next controls are mandatory.
- Snap is gentle, not forced scroll-jacking.
- Progress indicator is visible when the rail exceeds one screen.

Mobile:

- Native horizontal scroll or vertical stack.
- Content remains reachable without drag gestures.

## 14. Accordion and Disclosure

- 220–300ms height/opacity transition.
- Icon rotates 90–180°.
- Content is available with JS disabled when practical for critical information.

## 15. Page Transition

Native navigation is preferred.

If SPA transition exists:

```text
exit content 160–220ms
new content enters 280–420ms
header remains stable
```

Institutional wayfinding must not disappear during decorative transitions.

## 16. Loading States

- Skeletons mirror final geometry.
- Avoid pulsing gradients; use subtle opacity if skeletons are necessary.
- Critical text can load before imagery.
- Event lists show stable placeholders to prevent layout shift.

## 17. Reduced Motion

All non-essential motion is removed under `prefers-reduced-motion`.

Mega menus retain instant or near-instant open/close behavior. Sticky priority media becomes static sequential media.

## 18. Interaction Budget

Per screen:

- One primary interaction pattern.
- One supporting hover pattern.
- No competing scroll-based animation layers.

A page fails when the motion is more memorable than the information hierarchy.