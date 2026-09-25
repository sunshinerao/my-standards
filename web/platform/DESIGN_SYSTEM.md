# Platform Design System v1.0

## 1. Identity

**Platform = institutional clarity + editorial authority + global convening + measurable action.**

The system feels credible before it feels decorative. It uses disciplined alignment, white space, hierarchy, documentary media, strong information architecture and deliberate editorial sequencing.

Primary reference role:

- **United Nations:** institutional clarity, predictable navigation, multilingual thinking, accessibility, branding consistency, calm blue/neutral visual language.
- **The Rockefeller Foundation:** homepage narrative, issue framing, “priority → results → human story → news” sequence, high-quality media, interactive reporting and measured motion.
- **Climate Week NYC:** event programme, theme taxonomy, calendar, map and event-discovery mechanics.
- **London Climate Action Week:** distributed ecosystem, partner-led programme logic and city-wide network framing.

## 2. Brand Character

```text
Authoritative, not bureaucratic.
Global, not generic.
Editorial, not magazine-like.
Calm, not passive.
Modern, not fashionable.
Open, not visually noisy.
Institutional, not corporate.
```

## 3. Color System

The palette is UN-inspired, not a reproduction of UN identity.

```css
:root[data-mode="platform"] {
  --x-bg: #F7F8F8;
  --x-surface: #FFFFFF;
  --x-ink: #111719;
  --x-ink-soft: #4A555A;
  --x-line: #D5DDE1;

  --x-blue: #2E7FB6;
  --x-blue-deep: #185A84;
  --x-sky: #DCECF5;
  --x-sky-soft: #EFF6FA;
  --x-teal: #397F7A;
  --x-sand: #E9E5DB;
  --x-accent: #77B8D9;
}
```

Rules:

- White/off-white dominates.
- Blue is the institutional anchor.
- Black/ink carries headlines and navigation.
- Secondary colors identify themes; they do not decorate generic sections.
- Bright environmental green is not a default Platform brand color.
- Gradients are prohibited in the base identity.

## 4. Typography

### Preferred

- **Primary:** Roboto / Arial / Helvetica / system sans.
- **Optional editorial accent:** Source Serif 4 only for long-form quotations, reports or historical content.
- **Chinese fallback:** Noto Sans SC / Source Han Sans SC / PingFang SC.

### Scale

```css
--x-display-xl: clamp(3.8rem, 7vw, 7.4rem);
--x-display-lg: clamp(3rem, 5vw, 5.6rem);
--x-h1: clamp(2.8rem, 4.5vw, 5rem);
--x-h2: clamp(2rem, 3.2vw, 3.6rem);
--x-h3: clamp(1.4rem, 2vw, 2.25rem);
--x-body-lg: clamp(1.125rem, 1.35vw, 1.4rem);
--x-body: 1rem;
--x-meta: .75rem;
```

Rules:

- Display weight: 500–700.
- Body: 400.
- Labels: 500–700.
- Large institutional statements use compact tracking, not ultra-condensed decorative type.
- All-caps is limited to metadata, programme labels and small navigation utility text.

## 5. Layout Grammar

Platform pages use a **strict shared grid** with selective full-bleed interruptions.

Approved forms:

1. Full-width hero with aligned editorial copy.
2. 5/7 or 6/6 editorial split.
3. Priority/issue list with oversized numbering.
4. Metric band.
5. Story/video rail.
6. News list with strong date hierarchy.
7. Report/data feature.
8. Event filter + list/map.
9. Partner/logo field.
10. Institutional footer.

Default geometry is square or near-square. Rounded UI is rare.

## 6. Homepage Anatomy

The default Platform homepage follows this order:

### 01 — Hero / Current Proposition

- 72–94svh depending on media.
- One institutional statement.
- One supporting sentence.
- 1 primary CTA; 1 text link maximum.
- Hero may be image, video or a restrained editorial composition.

### 02 — Who We Are / Why This Platform Exists

- Strong statement + concise institutional paragraph.
- A current report or strategic document may be featured adjacent.
- No icon grid.

### 03 — Current Priorities

Rockefeller-style issue framing.

- 3–6 priorities.
- Large numbers or labels.
- Each priority includes one meaningful outcome statement.
- One priority may own the media area at a time.
- Desktop may use a controlled sticky media/content relationship.

### 04 — Results

- 3–5 metrics.
- Large type.
- Year/scope labels required.
- Link to methodology/report where appropriate.

### 05 — Stories Behind the Work

- Human-centered video or documentary image.
- 2–4 selected stories.
- Editorial rhythm takes precedence over card uniformity.

### 06 — Programme / Events

- Date, format, theme, location and access status are scannable.
- Calendar and map links are first-class controls.
- Filters remain compact.

### 07 — Insights / Reports / News

- News is chronological.
- Reports are visually distinct from news.
- Dates remain visible.
- The homepage shows only a curated subset.

### 08 — Network / Partners

- Logos are optically normalized.
- Partner tiers are not communicated through arbitrary logo size unless contractually required.

### 09 — Institutional Footer

- Navigation, contact, legal, privacy, accessibility and language access.
- Footer is structurally stable across the site.

## 7. Image System

### Subject Priority

```text
1. People convening, deciding, building, implementing
2. City and infrastructure
3. Field action and community context
4. Technology / systems / industry
5. Evidence, maps and data visualization
```

### Photography Direction

- Documentary and editorial.
- Avoid generic executive handshakes.
- Conference photography must show interaction, not only podiums.
- Urban imagery should show systems and people, not skyline-only tourism.
- Technical imagery should remain understandable to non-specialists.
- Captions and credits are part of the content model.

## 8. Core Components

### `PlatformHero`

Fields:

```text
eyebrow?
headline
supporting_line
primary_cta
secondary_link?
media
media_credit?
```

### `InstitutionStatement`

- 6–9 columns desktop.
- Can pair with report card or current announcement.
- No visual chrome around the paragraph itself.

### `PriorityStack`

Fields:

```text
index
priority_name
outcome_statement
summary
cta
media?
```

Desktop default:

- Text stack: 5–6 columns.
- Media: 6–7 columns.
- Current item visually active.

### `MetricField`

- Large numbers, minimal decoration.
- Metrics include unit, date and scope.
- Source link optional but recommended for externally asserted metrics.

### `StoryRail`

- Video and image stories may coexist.
- 3:2 default media ratio.
- Story title is primary; content type and geography are metadata.

### `EventCard`

Required fields:

```text
title
date/time
location or online
format
theme
public/private/access status
host
registration state
```

UI remains flat. Status is not communicated by color alone.

### `EventExplorer`

Contains:

- Calendar/list switch.
- Map switch where geographic density warrants it.
- Theme filters.
- Date filters.
- Location filters.
- Access filters.
- Search.

Filters must be URL-addressable when feasible.

### `ReportFeature`

- Cover or data visualization.
- Publication date.
- Short conclusion statement.
- Download/read actions.
- File size/type when downloadable.

### `NewsList`

- Date column.
- Headline column.
- Category/region optional.
- Minimal thumbnails; not every news item requires an image.

### `PartnerField`

- Neutral logo field.
- Grid aligns by optical weight.
- Monochrome or approved partner marks.
- Avoid decorative logo carousel unless partner count is extremely high.

### `PlatformFooter`

- Dark neutral or deep institutional blue.
- Primary site map.
- Legal links.
- Accessibility link.
- Privacy.
- Contact.
- Language access where relevant.

## 9. Buttons and Links

Platform default:

```text
height: 46–52px
radius: 0–2px
border: 1px solid currentColor
```

Primary actions may use filled blue; secondary actions use outline or text link.

Links are explicit. Avoid standalone “Read more” when a descriptive label is available.

## 10. Navigation Architecture

Primary navigation target: 5–6 items.

Recommended information categories:

```text
About
Priorities / Themes
Programme / Events
Stories / Insights
Network / Partners
Resources
```

Utility zone may contain:

```text
Search
Language
Register / Participate
Account / Passport / Portal
```

Utility actions do not compete typographically with core navigation.

## 11. Event Ecosystem Rules

The site treats events as structured data, not editorial posts.

Each event is filterable by:

- Date.
- Theme.
- Format.
- Location.
- Audience/access.
- Host.

Map and calendar are alternative views over the same event data source.

The system supports distributed host-led programming. The platform remains the discovery and trust layer even when the event is produced by a partner.

## 12. Page Types

Approved templates:

- Homepage
- About / Governance
- Priority / Theme
- Initiative
- Programme Overview
- Event Explorer
- Event Detail
- Venue / Hub
- Speaker / Contributor
- Story / Case Study
- News
- Insight / Perspective
- Report / Resource
- Results / Impact
- Partner / Network
- Media
- Contact

## 13. Mobile Rules

- Institutional hierarchy remains intact.
- Mega menus become full-screen navigation.
- Priority stacks become vertical accordions or sequential blocks.
- Event filters use a dedicated filter drawer.
- Map never replaces the event list; list remains available.
- Tables transform into labeled rows rather than horizontal overflow where possible.

## 14. Signature Test

A Platform page is on-system when:

- It feels trustworthy before it feels trendy.
- Header-to-footer alignment is consistent.
- A current priority is more visible than generic organization copy.
- Results are visible without hunting through reports.
- Human stories follow strategic framing.
- Events and resources are structured for discovery.
- Motion is noticeable through refinement, not volume.
- Accessibility and multilingual expansion are built into the layout.