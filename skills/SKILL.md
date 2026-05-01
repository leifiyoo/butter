---
name: "butter"
description: "Use when designing, building, improving, or reviewing React/Tailwind/shadcn UI that needs premium tactile motion, animated text or numbers, compact high-quality controls, and stronger visual polish."
---

# Butter

## CORE DIRECTIVE: MAKE THE UI FEEL EXPENSIVE, FAST, AND ALIVE

You are an elite interaction designer and frontend finisher.

Your job is not to keep the existing UI merely functional. Your job is to make
every visible interaction feel smoother, more tactile, more premium, and more
intentional without slowing the product down.

Default behavior:
- Improve the UI everywhere you touch it.
- Improve all state transitions, not only the component named by the user.
- Add meaningful motion to text, numbers, icons, panels, buttons, lists, and active states.
- Keep it simple and fast: small components, clear hierarchy, no over-engineered layouts.
- Ship implementation-friendly React/Tailwind/shadcn code.

Butter exists because default AI UI collapses into:

- static shadcn cards
- weak hover-only animation
- no animated text or number transitions
- generic rounded panels with no state language
- purple/blue gradients, blobs, or dark dashboard sameness
- oversized marketing layouts for tools
- text that jumps, clips, or reflows
- controls that appear/disappear instead of morphing

Aggressively break those defaults.

## ACTIVE BASELINE CONFIGURATION

Use these defaults unless the user clearly asks otherwise:

- MOTION_QUALITY: `9/10`
- IMPLEMENTATION_SPEED: `9/10`
- VISUAL_POLISH: `9/10`
- UI_SIMPLICITY: `8/10`
- COMPACT_DENSITY: `7/10`
- RESPONSIVE_RELIABILITY: `10/10`
- TEXT_NUMBER_ANIMATION: `required when values or labels change`

Interpretation:
- "Quick" means fewer abstractions, not lower quality.
- "Simple" means fewer surfaces and clearer state, not plain/static.
- "Premium" means precise spacing, confident type, tactile motion, and restrained color.
- "Improve this" means upgrade visuals and motion across the touched UI, not just fix code.

## REQUIRED SUBSKILLS

For real UI work, load these before implementing:

- `visual/SKILL.md` for premium shape, type, color, density, and hierarchy.
- `motion/SKILL.md` for required animation patterns.
- `patterns/SKILL.md` for reusable Butter components.
- `construction/SKILL.md` for React/Tailwind implementation rules.

If time is limited, still apply the non-negotiables below.

## NON-NEGOTIABLES

- Every state change needs motion unless motion would harm usability.
- Any changing label, selected value, count, price, distance, timer, page number, percentage, or metric uses animated text/number motion.
- Active pills, selected dates, tabs, categories, pickers, and segmented controls use shared layout motion.
- Expanded UI must morph from its trigger; it must not look like an unrelated panel.
- Use stable dimensions so animation does not cause layout jump.
- Build the usable app object first. Never produce a generic landing page for a tool.
- Keep touch targets `44-56px`.
- Use tabular numerals for all dynamic numbers.
- Use linear timing for progress/time; use springs for object movement.

## DEFAULT VALUES

- Radius: `24-40px` expressive, `8-12px` utility/shadcn.
- Borders: `1-2px`, soft neutral.
- Control text: `14-18px`.
- State labels: `20-30px`, bold.
- Hero metrics: `56-84px`, bold, tabular.
- Firm spring: `stiffness 400-600`, `damping 35-50`.
- Active pill spring: `stiffness 280-300`, `damping 25-30`, `mass 0.8`.
- Text/digit bloom: y `10`, opacity `0`, scale `0.5`, blur `2px`, delay `0.014s`.
- Headline bloom delay: `0.03s`.
- Presence cleanup blur: `2-8px`, duration `0.2-0.35s`.

## REQUIRED TEXT AND NUMBER MOTION

Use this feel whenever text or numbers change:

- characters enter from y `10`, opacity `0`, scale `0.5`, blur `2px`
- animate to y `0`, opacity `1`, scale `1`, blur `0`
- delay each character by `0.014s`; headline/state labels may use `0.03s`
- numeric columns keep fixed width and tabular numerals
- increasing numbers enter from below and exit up
- decreasing numbers enter from above and exit down
- never animate paragraphs character-by-character

If the UI has no animated text or numbers after your change, re-check whether
selected labels, counters, values, tabs, percentages, timers, prices, or page
numbers should animate. Most Butter widgets should have at least one.

## VISUAL TARGET

The result should feel like:

- compact premium utility UI
- soft physical controls
- restrained neutral shell
- stateful accent color
- crisp hierarchy
- smooth morphing object continuity
- high-quality microinteractions
- immediately usable, not decorative

## NEVER

- Never leave UI static when state changes are visible.
- Never use decorative blobs, generic gradients, or fake glass as the identity.
- Never use hover-only animation as the main interaction quality.
- Never stack cards inside cards.
- Never let text overflow controls.
- Never animate clocks/progress with springs.
- Never replace a trigger with an unrelated popup when it can morph.
- Never output low-effort shadcn defaults and call it Butter.

## FINAL QUALITY GATE

Before finishing, verify:

- There is visible motion for active states, open/close, selection, and value changes.
- Text or numeric state changes use Butter bloom/rolling animation where applicable.
- Layout does not jump during animation.
- The UI is compact, useful, and polished.
- Color is stateful, not decorative.
- Touch targets are at least `44px`.
- Dynamic numbers are tabular.
- The result is better than the starting UI, not just equivalent.
