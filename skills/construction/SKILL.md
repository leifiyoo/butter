---
name: "butter-construction"
description: "Use when implementing Butter components while preserving design quality: composition rules, state-to-geometry mapping, data boundaries, accessibility, and production pitfalls."
---

# Butter Construction

This file keeps only construction rules that affect design output.

## Object Model

- State drives geometry. Derive corners, borders, width, active backgrounds, and visibility from explicit mode/state.
- Prefer finite modes over loose booleans: idle/running/done, error/loading, recording/reviewing/playing.
- One temporary object should own its own local draft state; parent gets the committed result.
- For controlled widgets, support a controlled value and local default value only when reuse demands it.

## Composition

- Separate shell, trigger, content, and action layers. Each layer has one job.
- Use shared layout ids for active pills, selected dates, trigger-pill-to-tab-rail morphs, button-to-panel morphs.
- Use transparent native inputs when animated presentation text is required. Native input remains the interaction layer.
- Keep action buttons `shrink-0`; let only the center content flex.

## Measurement And Portals

- Use measured height for disclosure panels, QR panels, search/input morphs, and floating islands when content height is unknown.
- Use portals for fixed floating UI that must escape scroll containers or stacking contexts.
- Gate portals behind mounted state.
- Use viewport-aware width constraints: `max-w-[calc(100vw-32px)]`, `calc(100vw-80px)` for mobile search.

## Data And Derivation

- Derive display values from one source: amount conversion, scroll progress, page number, distance, selected date, selected agent.
- Avoid duplicating derived state unless it is the editable inverse of another field.
- Numeric input accepts empty or decimal regex only: `/^\d*\.?\d*$/`.
- Currency conversion: convert through shared base rate; footer rate comes from selected currencies, not current amount.
- Calendar/event maps use ISO date keys; selected date uses the same format.

## Interaction Contracts

- Outside click closes lightweight floating pickers/dropdowns.
- Enter should trigger the same primary action as the visible button in compact input flows.
- Escape/clear should return to the neutral state and reset temporary values when low-risk.
- Selecting from single-choice popovers closes the popover immediately.
- Confirm buttons are used when a setting has dependent temporary choices.

## Accessibility And Semantics

- Indicators that change value or navigation should be buttons, not inert divs.
- Use `aria-expanded` for pickers/disclosures and `role="menu"` for compact option shelves.
- Title icon buttons and close/remove buttons need labels or titles.
- Disabled visuals must match disabled behavior.

## Timers And Cleanup

- Intervals belong to the mode that uses them and must be cleared on mode exit and unmount.
- Temporary copied/loading states use timeouts with cleanup.
- Recording/playback timers are independent; playback countdown must not mutate recorded duration.
- Resize/scroll/document listeners must be removed.

## Media And Assets

- Use real flags/logos/avatars when identity matters, with fallback: flag CDN + emoji, avatar fallback, QR SVG.
- Do not fake precise audio analysis; abstract bars are acceptable only as a recording proxy.
- If a component implies a payload, pass the payload shape cleanly: resolved entity, selected context, rating+feedback, voice duration/blob.

## Production Pitfalls

- Remove debug logs from drag/snap/submit handlers.
- Never randomize visual data on every render; generate once and store.
- Do not silently ignore synchronization hooks that the surrounding product expects.
- Do not use brittle fixed heights when content is dynamic and visible.
