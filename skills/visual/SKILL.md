---
name: "butter-visual"
description: "Use when deciding Butter visual language: color, radius, density, typography, icon treatment, hierarchy, and what makes a UI stop feeling like Butter."
---

# Butter Visual

Butter is compact, soft, precise app UI. It feels like useful objects on a desk: rounded, touchable, low-noise, and quietly premium.

## Shape

- Default component shells: `24-40px` radius for pills/cards, `8-12px` for utilitarian shadcn-compatible variants.
- Use radius as state language: connected groups share edges; active/expanded objects regain full radius.
- Keep controls as one object when possible: button becomes input, dot becomes progress pill, icon button becomes panel.
- NEVER stack cards inside cards. Repeated items can be cards; page sections and control groups should be shells, rails, pills, or bands.

## Surfaces

- Primary shells: near-white `#FEFEFE`, soft gray `#F4F4F9`, `#F6F5FA`, or dark `#14141A-#1C1C1E`.
- Borders: `1-2px`, very quiet: `#E5E5E9`, `#ECECEF`, `#F0EFF6`, `white/5-10%` in dark.
- Shadows: small and close for controls; larger only for floating cards or popovers. Avoid dramatic marketing shadows.
- Use muted panels for grouped inputs, meters, event lists, and settings editors.
- NEVER use decorative gradient blobs, generic glass hero effects, or loud saturated backgrounds as the main Butter identity.

## Color

- Butter is mostly neutral; color is stateful. Use color for success, destructive, selected category identity, or active product context.
- Active state may use a soft tinted background plus strong text: e.g. red text on `#F9EBEF`, green confirmation, blue action.
- Disabled/secondary text: muted gray around `#8C8C8A`, `#9F9EA1`, `#AFAFAF`.
- Primary dark action: `#262629`, `#282828`, or foreground token; primary light action in dark mode: near-white.
- NEVER make the UI one-note purple/blue, beige-only, or all dark-slate. Neutral is base, not palette laziness.

## Type

- Use confident weights: labels and button text `600-800`; secondary copy `500-600`.
- Compact control text: `14-18px`; major widget metrics: `56-84px`, bold, tabular.
- Current state labels can be headline-sized above controls: `24-30px`, extra-bold.
- Use tabular numerals for counters, page numbers, prices, miles, time, and scrub values.
- Letter spacing stays normal; do not use negative tracking.

## Icons

- Icons are functional, not decorative. Use them for mode, category, status, and action recognition.
- Common icon sizes: `18-22px` inside compact controls, `24-28px` for primary buttons, `32-34px` for card shortcut actions.
- Active icon may scale only slightly (`1.03-1.1`). Avoid cartoon bounce.
- Chevrons stay muted and rotate; they do not need strong color.

## Layout Rhythm

- Butter is dense but comfortable: control padding usually `6-16px`, gaps `4-12px`.
- Large cards often use `p-6`/`p-8`; compact rails use `p-1`/`p-1.5`.
- Fixed touch targets: `44-56px` for arrows, icon buttons, send buttons, calendar dates.
- Keep action anchors stable: submit on right, destructive/close nearby but secondary, primary CTA at bottom for cards.

## Repeated Visual Patterns

- **Shared active pill:** moving background under tabs, categories, options, segmented toggles.
- **Input overlay:** transparent native input above animated digits for money/amount entry.
- **Floating value bubble:** selected scrub/ruler value above center marker.
- **Horizontal rail:** dates, tick rulers, category choices, and compact popovers.
- **Entity chip:** resolved pasted value with avatar/name/remove in same field.
- **Bottom fade:** scrollable panels get subtle gradient fade, not heavy scroll chrome.

## NEVER

- Never add explanatory text inside the app that tells users how the UI works.
- Never let text overflow its control; use fixed dimensions, truncation, or responsive constraints.
- Never make expanded states feel like unrelated components. They must read as the same object changing role.
- Never use color when shape, position, or weight can carry the state more quietly.
