---
name: "butter-motion"
description: "Use when UI feels static, cheap, jumpy, or lacks premium animation for text, numbers, panels, active states, controls, drag, progress, and state transitions."
---

# Butter Motion

## CORE DIRECTIVE: ANIMATE EVERY MEANINGFUL STATE CHANGE

Butter motion is not decoration. It is the quality layer that makes the UI feel
expensive, responsive, and understandable.

Default assumption: if state changes visibly, motion is required.

Upgrade:
- label changes
- numeric values
- selected tabs/categories/options
- buttons becoming inputs or panels
- dropdowns/popovers
- list entries
- icons swapping
- progress/timers
- drag/scrub/ruler controls
- error/success/copy/send feedback

Do not leave a Butter component feeling static.

## Spring Palette

- Firm object movement: `stiffness 400-600`, `damping 35-50`, `mass 0.8-1.2`.
- Shared active pill: `stiffness 280-300`, `damping 25-30`, `mass 0.8`.
- Friendly morph: `bounce 0.15-0.3`, `duration/visualDuration 0.35-0.7`.
- Text/digit bloom: `stiffness 200-240`, `damping 16-20`, `mass 1.2`.
- Tap feedback: scale `0.9-0.97`.
- Hover feedback: y `-1` or scale `1.03-1.06`, never loud bounce.

## Required Text Animation

Use for selected tab labels, option labels, app type labels, changing button
text, copied states, mode labels, and compact state headlines.

Pattern:
- split text into characters
- y `10 -> 0`
- opacity `0 -> 1`
- scale `0.5 -> 1`
- filter `blur(2px) -> blur(0px)`
- delay `0.014s * index`
- use `0.03s * index` for prominent state labels
- preserve spaces with non-breaking spaces

Exit:
- y `-10`
- opacity `0`
- scale `0.5`
- blur `2px`

Never animate long paragraphs character-by-character.

## Required Number Animation

Use for:
- page numbers
- prices/currency
- timers
- percentages
- distances
- ratings
- counts
- scrub values
- metrics

Pattern:
- use tabular numerals
- keep fixed digit columns
- compare previous value to current value
- increasing: enter from y `8-20`, exit y `-8/-20`
- decreasing: enter from y `-8/-20`, exit y `8-20`
- opacity `0 -> 1`, scale `0.5 -> 1`, blur `2px -> 0`
- decimals keep stable precision when the domain expects it
- use NumberFlow-style rolling for big metrics

If a number changes instantly with no animation, it is not Butter.

## Morph Rules

- Animate size, radius, border, background, and internal positions together.
- Trigger and expanded state must feel like the same object.
- Use shared layout ids for active pills, selected dates, tabs, trigger-to-panel, and icon-to-input.
- Use measured height for unknown panels.
- Use blur only during transition cleanup: `2-8px`.
- Do not use blur as ambient decoration.

## Presence Choreography

- Standard enter: opacity `0 -> 1`, y `5-15 -> 0`, scale `0.5-1`, blur `2-4 -> 0`.
- Popover enter: opacity, y `-8/10`, scale `0.96-1.1`, blur `4`.
- Icon swap: opacity, scale `0.25-0.8 -> 1`, blur `4 -> 0`, duration `0.2-0.3s`.
- List rows: y `10-15`, blur `4`, duration `0.3s`, slight stagger.
- Backdrop: opacity only, no fancy motion.

## Time Is Linear

Use linear timing for:
- progress bars
- recording borders
- playback countdowns
- upload/loading progress
- auto-advance timers

Never spring elapsed time. Physics for objects; linear for clocks.

## Drag And Scrub

- Drag elasticity `0-0.1`.
- Precision controls clamp internally and track pointer globally.
- Fixed marker with moving scale for rulers/scrubbers.
- Snap with `stiffness 400`, `damping 40`.
- While dragging, lift value bubble y `-4`, scale `1.05`.

## Feedback

- Copy/sent/success text blooms, do not just swap instantly.
- Error can wobble rotate `-2, 2, -1, 1, 0`.
- Retry slides from behind status with x `-55`, blur `4`, scale `0.8`.
- Disabled controls do not animate lively.

## Final Motion Check

Before shipping:
- At least one meaningful text or number transition exists when state changes.
- Open/close has presence animation.
- Active selection uses shared layout motion.
- Motion improves clarity and does not slow the task.
