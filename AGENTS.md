# Agent Instructions

## Butter UI Work
For any frontend, UI, design, component, Tailwind, React, or shadcn task in this repo, use Butter.

Core directive: improve the touched UI everywhere. Add premium motion, animated text/numbers, stronger hierarchy, better spacing, and tactile state changes. Do not only preserve existing behavior; make the result visibly higher quality.

Read in order:
1. `skills/SKILL.md`
2. `skills/visual/SKILL.md`
3. `skills/motion/SKILL.md`
4. `skills/patterns/SKILL.md`
5. `skills/construction/SKILL.md` when implementing code

Do not replace Butter with generic shadcn, card-stack, dashboard, or landing-page defaults.

Before finalizing UI, check:
- visible motion for state changes, open/close, selection, and feedback
- changing labels or values use Butter text/number bloom
- compact app object, not marketing page
- expressive radius `24-40px` or utility radius `8-12px`
- quiet neutral shell, stateful color only
- stable controls and touch targets `44-56px`
- Butter springs for tactile changes; linear timing for progress
- tabular numerals, semibold/bold labels, no thin text
- text does not overflow on mobile or desktop
- no decorative blobs, generic gradients, explanatory UI copy, or nested cards
