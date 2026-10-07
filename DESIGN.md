---
name: Dárquia Moreira, Psicóloga Clínica
description: Calm pearl-and-graphite one-pager with a single matte-gold accent, built to turn first visits into WhatsApp conversations.
colors:
  pearl: "#F6F6F4"
  pearl-deep: "#ECECE8"
  gold-tint: "#EEE7D6"
  surface: "#FBFBFA"
  graphite: "#1F2123"
  graphite-soft: "#4E5356"
  hairline: "#D6D6D1"
  matte-gold: "#A88646"
  gold-ink: "#7A5F2B"
  band-gold: "#C9A765"
  night: "#141617"
  night-raised: "#1D2021"
typography:
  display:
    fontFamily: "Outfit, system-ui, sans-serif"
    fontSize: "clamp(2.5rem, 0.8rem + 3.2vw, 3.625rem)"
    fontWeight: 600
    lineHeight: 1.05
    letterSpacing: "-0.03em"
  headline:
    fontFamily: "Outfit, system-ui, sans-serif"
    fontSize: "clamp(2rem, 1.2rem + 2.8vw, 3.25rem)"
    fontWeight: 600
    lineHeight: 1.1
    letterSpacing: "-0.025em"
  title:
    fontFamily: "Outfit, system-ui, sans-serif"
    fontSize: "1.375rem"
    fontWeight: 600
    lineHeight: 1.25
    letterSpacing: "-0.01em"
  body:
    fontFamily: "Figtree, system-ui, sans-serif"
    fontSize: "1.0625rem"
    fontWeight: 400
    lineHeight: 1.65
  label:
    fontFamily: "Figtree, system-ui, sans-serif"
    fontSize: "1.0625rem"
    fontWeight: 600
    lineHeight: 1.2
rounded:
  tile: "16px"
  pill: "999px"
spacing:
  gap: "16px"
  tile-pad: "36px"
  section-y: "112px"
components:
  button-primary:
    backgroundColor: "{colors.graphite}"
    textColor: "{colors.pearl}"
    rounded: "{rounded.pill}"
    padding: "12.8px 25.6px"
    height: "52px"
  button-primary-hover:
    backgroundColor: "{colors.matte-gold}"
    textColor: "{colors.graphite}"
  tile:
    backgroundColor: "{colors.pearl-deep}"
    textColor: "{colors.graphite}"
    rounded: "{rounded.tile}"
    padding: "36px"
  tile-ink:
    backgroundColor: "{colors.graphite}"
    textColor: "{colors.pearl}"
    rounded: "{rounded.tile}"
    padding: "36px"
---

# Design System: Dárquia Moreira, Psicóloga Clínica

## Overview

**Creative North Star: "The Quiet Consulting Room"**

The page behaves like the room it advertises: pearl walls, graphite furniture, one small piece of gold, and her face as the warmest thing in view. Nothing shouts. Trust comes from space, from patients' own words in large type, and from a single obvious action (WhatsApp) repeated calmly. Density is low, motion is a gentle settling, and every surface has one job.

The system refuses two familiar looks: the dark-mesh, purple-glow health-tech landing, and the cream-and-brass "wellness" template. Warmth lives in the photography and in one gold-tinted tile, not in the ground color.

**Key Characteristics:**
- Cool pearl ground, graphite ink, one matte-gold accent used for graphics, filets and hover fills.
- Sans-only type: Outfit for voice, Figtree for reading.
- 16px tiles and pill buttons; no shadows at rest.
- Light by default, dark mode automatic with the same token names.

## Colors

A restrained palette: cool neutrals plus a single gold, locked page-wide.

### Primary
- **Graphite** (#1F2123): text, primary buttons, and the single dark tile and band that anchor the page.

### Secondary
- **Matte Gold** (#A88646): stars, icons in tiles, underline accents, button hover fill. Never body text on light grounds (about 3.2:1).
- **Gold Ink** (#7A5F2B): the text-safe gold, used for small icons and hover text on pearl (about 5.5:1).
- **Band Gold** (#C9A765): the same gold lifted for use on graphite surfaces.

### Neutral
- **Pearl** (#F6F6F4): page ground.
- **Pearl Deep** (#ECECE8): resting tile fill.
- **Gold Tint** (#EEE7D6): one tile at most per section, for warmth.
- **Surface** (#FBFBFA): quote cards and an opened FAQ item.
- **Graphite Soft** (#4E5356): secondary text (about 7:1 on pearl).
- **Hairline** (#D6D6D1): 1px outlines.
- **Night** (#141617) and **Night Raised** (#1D2021): dark-mode ground and tile fill.

### Named Rules
**The One Gold Rule.** Gold is the only accent. It appears as graphic marks, filets and hover fills, and the text-safe Gold Ink handles any gold that must be read.
**The Pearl Not Cream Rule.** The ground stays cool and near-white. Warmth is allowed in one tinted tile per section, never in the page field.

## Typography

**Display Font:** Outfit (with system-ui sans-serif)
**Body Font:** Figtree (with system-ui sans-serif)

**Character:** Outfit's geometric, slightly rounded forms read friendly without turning childish; Figtree keeps long Portuguese copy easy. Weights 300, 400, 500 and 600 only, so hierarchy comes from weight and size, never from a second family.

### Hierarchy
- **Display** (600, clamp 2.5-3.625rem, 1.05): the hero headline, two lines on desktop.
- **Headline** (600, clamp 2-3.25rem, 1.1): section headings.
- **Title** (600, 1.375rem, 1.25): tile and plan headings.
- **Body** (400, 1.0625rem, 1.65): paragraphs, capped near 62ch.
- **Label** (600, 1.0625rem, 1.2): buttons. Featured patient quote uses Outfit 300 at clamp 1.5-2.25rem.

### Named Rules
**The Same Family Rule.** Emphasis is weight or size inside Outfit or Figtree; no mixed-family flourishes.
**The No Eyebrow Rule.** Headings stand alone, without small labels above them.

## Layout

One page, 1200px container, 20px gutters on phones and 32px from `lg`. Sections breathe at 80px (mobile) to 112px (desktop) of vertical padding. The hero is a 7/5 split that fits one desktop viewport; the treatments are a 12-column bento with 7/5 and 5/7 rows; reviews pair one featured quote (5 cols) with a 2x2 set (7 cols); plans are one wide band over two half tiles; FAQ is a 4/8 split. Every asymmetric layout collapses to a single column below 1024px.

## Elevation & Depth

Flat by default. Depth comes from tonal layering (pearl, pearl deep, graphite) and a single offset tinted plate behind the hero photo. The only shadows are a soft graphite shadow under the name chip and under buttons on hover (`0 10px 24px -12px rgb(31 33 35 / .45)`). Tiles lift by 3px on hover with no shadow.

### Named Rules
**The Flat At Rest Rule.** Surfaces carry no shadow until a state asks for one.

## Shapes

One radius scale: 16px on images, tiles, quote cards and FAQ items; pill (999px) on buttons, chips, avatars and social buttons. No sharp or mixed corners.

## Components

### Buttons
- **Shape:** pill, 52px tall minimum.
- **Primary:** graphite fill, pearl text, WhatsApp glyph at left.
- **Hover / Focus:** fill turns Matte Gold with graphite text, lifts 2px; active presses to 0.98 scale. Focus is a 3px Gold Ink ring (Gold Ink lightened in dark mode), offset 3px.
- **On band:** pearl fill, graphite text; hover Band Gold.
- **Quiet link:** graphite text with a 2px gold underline.

### Chips
Outlined pills (1px hairline) for the TCC techniques; informational only.

### Tiles
Pearl Deep fill, 16px radius, 36px padding. Variants: outlined (hairline), gold-tinted, graphite. Icon at top in Gold Ink (Band Gold on graphite).

### Quote cards
Surface fill with a hairline; the featured one is graphite with light Outfit 300 type. Stars use Matte Gold, avatars are initials on Gold Tint.

### Navigation
Sticky 72px bar on the page ground, text wordmark at left, five links and one WhatsApp CTA. A hairline appears once scrolled. Below 1024px a hamburger opens a full-width panel with 24px links.

### FAQ
Native disclosure items as 16px tiles; the caret rotates when open.

## Do's and Don'ts

### Do:
- **Do** send every call to action to WhatsApp, with a message that matches the section.
- **Do** keep patients' reviews verbatim, with their Google attribution.
- **Do** use Gold Ink (#7A5F2B) whenever gold text is needed on a light ground.
- **Do** keep one gold-tinted tile per section at most.

### Don't:
- **Don't** publish session prices, opening hours or statistics that are not in her own sources.
- **Don't** introduce a second accent, a serif face, or gradient text.
- **Don't** put eyebrow labels above headings or number the sections.
- **Don't** use shadows at rest or hard offset shadows.
