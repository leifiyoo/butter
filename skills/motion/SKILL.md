---
name: "butter/motion"
description: "Use when designing Butter motion: springs, morphs, drag behavior, animated numbers, reveals, feedback, and motion rules that preserve the Butter feel."
---

# Butter Motion

Butter motion is tactile and contained. It explains object continuity: the user should see one object changing job, not a component swap.

## Spring Palette

- Firm layout snap: `stiffness 400-600`, `damping 35-50`, `mass 0.8-1.2`.
- Shared active pill: `stiffness 280-300`, `damping 25-30`, `mass 0.8`.
- Friendly morphs: `bounce 0.15-0.3`, `duration/visualDuration 0.35-0.7`.
- Text/digit bloom: `stiffness 200-240`, `damping 16-20`, `mass 1.2`.
- Tap feedback: scale `0.9-0.97`; hover scale only `1.03-1.06`.

## Morph Rules

- Animate size, radius, and internal positions together with layout motion.
- Button-to-input, QR button-to-panel, search icon-to-input, and summary-to-editor must feel like one object unfolding.
- Use measurement for unknown height panels; collapsed fixed height, expanded measured height.
- Blur is for transition cleanup only: `2-8px` paired with opacity/scale. NEVER use blur as ambient decoration.

## Presence Choreography

- Standard enter: opacity `0->1`, y `5-15px -> 0`, scale `0.5-1`, blur `2-4px -> 0`.
- Popover enter: opacity, y `-8/10px`, scale `0.96-1.1`, blur `4px`.
- Icon swaps: opacity, scale `0.25-0.8 -> 1`, blur cleanup in `0.2-0.3s`.
- Long content lists: rows enter with y `10-15px`, blur `4px`, duration `0.3s`.

## Text And Numbers

- Letter bloom: y `10`, opacity `0`, scale `0.5`, blur `2px`, delay `0.014s` per char.
- Slower headline labels: delay `0.03s` per char.
- Directional numbers: increasing enters from below and exits up; decreasing enters from above and exits down.
- Financial/metric values use rolling/NumberFlow motion; keep tabular width and fixed decimals when needed.
- NEVER animate long paragraphs letter-by-letter.

## Time Is Linear

- Progress fills, recording borders, audio playback, and carousel auto-progress use linear timing.
- Do not spring elapsed time. Physics for layout; linear for clocks.
- Common durations: active progress over `autoDelay`; recording border over `maxDuration`; subtle progress texture loop `0.5s linear`.

## Drag And Scrub

- Direct manipulation beats flourish. Drag elasticity `0-0.1`; no momentum for precision controls.
- Fixed marker with moving scale works for rulers, distance, scrubbers, and waveform playheads.
- Snap on release with firm spring: `stiffness 400`, `damping 40`.
- While dragging, lift/scale value bubble slightly: y `-4`, scale `1.05`.
- Track pointer globally during drag and clamp internally.

## Feedback Motion

- Small acknowledgement bursts may last `0.5s`, with radial particles scaling `0 -> 1.2 -> 0`.
- Errors can wobble subtly: rotate `-2, 2, -1, 1, 0`.
- Retry buttons may slide from behind status pill with x around `-55`, blur `4px`, scale `0.8`.
- Disabled controls do not receive lively tap/hover animation.

## NEVER

- Never animate everything just because motion is available.
- Never move text size, layout anchors, or main action position during state changes.
- Never make hover the main motion event for utility controls; click/tap/state change is the moment.
- Never leave motion that makes reading slower than the interaction value it adds.
