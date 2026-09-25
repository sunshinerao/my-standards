# Website Design System v1.0 — Validation Report

**Validation date:** 2026-09-24  
**Modes:** `Programme` / `Platform`  
**Verdict:** Both systems pass the implementation gate. The current reference implementations reach **88% Programme design-language fidelity** and **90% Platform design-language fidelity** against their assigned reference roles.

> “Fidelity” here means design-language fidelity: hierarchy, rhythm, media behavior, interaction quality, editorial pacing, navigation behavior and restraint. It does **not** mean pixel-for-pixel reproduction. Exact third-party layouts, brand assets, copy, proprietary illustrations and frame-for-frame animations are intentionally excluded.

---

## 1. Validation Method

The rules were tested by generating two independent homepage prototypes using only the files in this repository:

- `demos/programme-home.html`
- `demos/platform-home.html`

The prototypes were rendered at:

- Desktop: `1440 × 1000`
- Mobile: `390 × 844`
- Desktop menu-open state

The validation covered four layers:

1. **Rule compliance** — required structure, accessibility hooks, focus management, motion fallback, responsive behavior.
2. **Visual-system compliance** — color, type hierarchy, grid, spacing, image ratios, density and section rhythm.
3. **Interaction compliance** — header state, mega menu, keyboard close, focus trap, inert background, reveal behavior and reduced motion.
4. **Reference fidelity** — comparison to the assigned design roles of the reference sites.

The demo uses original abstract placeholder media and neutral placeholder data. It does not copy third-party imagery or claim fictional metrics as facts.

---

## 2. Programme — Validation Result

### 2.1 Implementation Gate

**Result: 20 / 20 — PASS**

Verified in the generated prototype:

- Skip link and main landmark.
- Responsive desktop/mobile composition.
- Media-led hero.
- Quiet manifesto section.
- Journey structure.
- Large editorial feature story.
- Story sequence without a dashboard-like card wall.
- Impact block secondary to narrative.
- Emotional closing CTA.
- Programme palette and typography hierarchy.
- No default large-radius card system.
- No scroll-jacking.
- `aria-expanded` menu state.
- Escape-to-close.
- Focus trap.
- Background `inert` while navigation is open.
- IntersectionObserver-based reveal.
- `prefers-reduced-motion` fallback.
- Semantic footer.
- Responsive media query.

### 2.2 Design-Language Fidelity

| Dimension | Weight | Score | Conclusion |
|---|---:|---:|---|
| Visual character / colour / atmosphere | 20 | 18 | Strong urgent-optimism character; quiet natural palette; avoids generic NGO styling. |
| Homepage narrative expression | 20 | 19 | Hero → meaning → journey → stories → impact → action reproduces the Earthshot-style story-first hierarchy. |
| Editorial rhythm / whitespace | 15 | 14 | Strong alternation between full-bleed, quiet text, feature story and grouped content. |
| Image / media language | 15 | 10 | System direction is correct, but prototype uses original abstract placeholders rather than documentary photography and film. |
| Interaction / motion | 15 | 13 | Fluid, staged and restrained; menu and reveals are implemented. Real media would strengthen cinematic transitions. |
| Responsive / accessibility | 15 | 14 | Mobile reflows correctly; keyboard/reduced-motion paths implemented. Production needs content-level accessibility QA. |
| **Total** | **100** | **88** | **88% design-language fidelity** |

### 2.3 Main Remaining Gap

The remaining gap is primarily **asset-level**, not system-level:

- Real documentary photography.
- Real hero film where appropriate.
- Final licensed/approved brand typography.
- Project-specific art direction and crops.
- Production copy and verified impact data.

The rule system should not be changed to close this gap. Production assets should be inserted into the existing system.

### 2.4 Reference Match

Primary reference role:

- The Earthshot Prize — visual character, optimistic environmental storytelling, media-led programme expression.
- Justified Studio Earthshot identity case study — renewal / forward motion, refined but accessible typography, colour and motion.
- IDEO.org / TED Countdown — project-led editorial logic and action/story balance.

Conclusion: **Programme is recognizably in the same design family without becoming a replica.**

---

## 3. Platform — Validation Result

### 3.1 Implementation Gate

**Result: 20 / 20 — PASS**

Verified in the generated prototype:

- Stable institutional header.
- Branding/utility layer above primary navigation.
- Current priorities before archives.
- Institutional statement and report feature.
- Results block.
- Strategic framing before human stories.
- Programme/event structure.
- Separate report/news treatment.
- Network/partner section.
- Institutional footer utility links.
- Signature mega menu with featured editorial media.
- `aria-expanded` state.
- Escape-to-close.
- Focus trap.
- Background `inert` while navigation is open.
- Restrained IntersectionObserver reveal.
- `prefers-reduced-motion` fallback.
- Responsive desktop/mobile composition.
- Platform blue/neutral token system.
- No generic large-radius/shadow card language.

### 3.2 Design-Language Fidelity

| Dimension | Weight | Score | Conclusion |
|---|---:|---:|---|
| UN-style institutional visual language | 20 | 18 | Strong white/blue/ink hierarchy, predictable navigation and disciplined information structure. |
| Rockefeller-style homepage expression | 20 | 19 | Position → priorities → results → stories → programme → insights closely matches the reference logic. |
| Navigation / mega menu / interaction | 20 | 17 | Large editorial menu, scrim, staged open/close and featured story pattern are implemented. Exact Rockefeller choreography is intentionally not copied. |
| Editorial rhythm / media treatment | 15 | 12 | Strong rhythm, but prototype uses abstract media rather than real editorial photography/video/data visualization. |
| Climate-week event architecture | 15 | 14 | Programme structure is designed for list/calendar/map views from one event data source; prototype shows the list state only. |
| Responsive / accessibility | 10 | 10 | Desktop/mobile, keyboard, inert background and reduced-motion paths are implemented. |
| **Total** | **100** | **90** | **90% design-language fidelity** |

### 3.3 Main Remaining Gap

The remaining gap is primarily in **production media and advanced data experience**:

- Real institutional/editorial photography.
- Production video and report visuals.
- Live data visualization.
- Full Calendar / Map / Filter event explorer.
- Final CMS data and multilingual content.
- Browser-level fine tuning of motion timing against final media weight.

The core homepage and interaction grammar should remain unchanged.

### 3.4 Reference Match

Primary reference roles:

- United Nations Web Guidelines — institutional consistency, branding layers, predictable navigation, multilingual/accessibility discipline.
- The Rockefeller Foundation — homepage narrative, priorities/results/stories sequence, editorial pacing, large-scale navigation quality.
- Climate Week NYC — calendar/map/theme-based event exploration.
- London Climate Action Week — partner-led programme ecosystem.

Conclusion: **Platform has stronger structural fidelity than literal visual similarity, which is the intended outcome for a reusable institutional platform.**

---

## 4. Reference Research Basis

### Programme

- The Earthshot Prize homepage: https://earthshotprize.org/
- The Earthshot Prize Earthshots: https://earthshotprize.org/the-prize/earthshots/
- Justified Studio — The Earthshot Prize identity: https://www.justified.studio/work/the-earthshot-prize
- IDEO.org: https://www.ideo.org/
- TED Countdown: https://countdown.ted.com/

### Platform

- United Nations Web Guidelines: https://www.un.org/en/webguidelines/
- UN — Design your website: https://www.un.org/en/webguidelines/design.shtml
- The Rockefeller Foundation: https://www.rockefellerfoundation.org/
- Rockefeller Foundation 2025 Impact Report: https://impactreport.rockefellerfoundation.org/
- Climate Week NYC: https://www.climateweeknyc.org/
- Climate Week NYC event map: https://www.climateweeknyc.org/official-map
- London Climate Action Week main programme: https://londonclimateactionweek.org/main-programme/

---

## 5. Final Decision

**Programme and Platform are approved as v1.0 reusable baselines.**

Future work should modify content, project identity tokens and approved assets **inside** the system. It should not redesign navigation behavior, spacing logic, motion grammar, component hierarchy or page rhythm unless an explicit version upgrade is requested.

Use:

```text
Use Website Design System v1.0 — Programme mode.
```

or:

```text
Use Website Design System v1.0 — Platform mode.
```

Any future AI-generated page scoring below **18/20** on the selected system's QA gate must be revised before delivery.