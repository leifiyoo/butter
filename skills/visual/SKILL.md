---
name: "butter-visual"
description: "Use when UI looks generic, low-quality, static, poorly spaced, overly shadcn-default, visually cheap, or missing premium Butter shape, type, density, color, and hierarchy."
---

# Butter Visual

## CORE DIRECTIVE: MAKE THE UI LOOK FINISHED

Butter UI should feel like a premium compact product object: soft, precise,
touchable, fast, and clearly useful.

Do not accept generic defaults. Upgrade every touched surface:
- better radius language
- stronger hierarchy
- cleaner spacing
- stable sizing
- stateful color
- confident typography
- meaningful icon treatment
- no decorative filler

## Active Visual Defaults

- VISUAL_POLISH: `9/10`
- SIMPLICITY: `8/10`
- COMPACT_DENSITY: `7/10`
- LOW_NOISE: `9/10`
- STATE_CLARITY: `10/10`

## Shape

- Expressive shells: `24-40px` radius.
- Utility/shadcn variants: `8-12px` radius.
- Connected groups share edges; active/expanded objects regain full radius.
- One object should transform roles: button -> input, chip -> editor, icon -> panel.
- Avoid anonymous rectangles. Every shell needs a clear job.

## Surfaces

- Light shells: `#FEFEFE`, `#F4F4F9`, `#F6F5FA`.
- Dark shells: `#14141A`, `#1C1C1E`, neutral zinc/graphite.
- Borders: `1-2px`, `#E5E5E9`, `#ECECEF`, `#F0EFF6`, `white/5-10%`.
- Shadows: close and soft for controls; larger only for floating cards/popovers.
- Muted panels group inputs, meters, settings, and lists.

## Color

- Neutral is the base. Color is state, category, status, or brand context.
- Active state can use soft tint + strong text, e.g. red text on `#F9EBEF`.
- Secondary text: `#8C8C8A`, `#9F9EA1`, `#AFAFAF`.
- Primary dark action: `#262629` or `#282828`.
- Dark-mode primary action: near-white.
- Never use one-note purple/blue, beige-only, all slate, decorative blobs, or generic gradients.

## Type

- Labels/buttons: weight `600-800`.
- Secondary copy: `500-600`.
- Compact controls: `14-18px`.
- State labels: `20-30px`, bold.
- Large metrics: `56-84px`, bold, tabular.
- Letter spacing: normal. No negative tracking.
- Dynamic numbers: always tabular.
- Changing labels/values: must pair with Butter text/number animation from `motion/SKILL.md`.

## Layout Rhythm

- Compact padding: `6-16px`.
- Compact gaps: `4-12px`.
- Card padding: `p-6`/`p-8`.
- Rails: `p-1`/`p-1.5`.
- Icon/touch controls: `44-56px`.
- Keep primary action anchors stable: send/right, confirm/right, destructive/close secondary, card CTA bottom.

## Components Should Read As Objects

Use:
- shared active pill
- segmented rail
- floating value bubble
- input overlay with animated digits
- entity chip
- compact popover shelf
- bottom fade on scrollable lists

Avoid:
- stacked generic cards
- dashboard card spam
- decorative hero composition
- random accent colors
- explanatory helper text

## Final Visual Check

Before shipping:
- The touched UI looks intentionally designed, not generated.
- There is a clear state hierarchy.
- Spacing is compact but breathable.
- Text fits inside every control.
- Dynamic labels/numbers have motion support.
- Nothing reads as a generic shadcn default.
