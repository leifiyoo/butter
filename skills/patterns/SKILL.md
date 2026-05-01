---
name: "butter/patterns"
description: "Use when choosing recurring Butter UI patterns: compact pickers, morphing controls, rails, tabs, status pills, input chips, media controls, and cards."
---

# Butter Patterns

Use these as decision shortcuts. Pick the pattern that matches the interaction, then apply Butter visual and motion rules.

## Morphing Controls

- **Button becomes field:** for one short input directly tied to an action.
- **QR reveal:** collapsed label button to measured scan panel; scan first, copy/close second.
- **Search-or-browse bar:** search icon expands; categories yield; close restores browse.
- **Summary-to-editor:** compact setting display opens into structured choices; commit with check when edits are dependent.

## Compact Selection

- **Shared active pill tabs:** peer categories with icon+label. Use moving background, not per-tab layout changes.
- **Horizontal option shelf:** 2-3 choices above trigger; use when all choices should be visible at once.
- **Cycle instead of dropdown:** only for tiny obvious sets like type/unit or two-mode controls.
- **Dot-to-icon step pager:** inactive dots, active icon, label above controls.

## Input And Resolution

- **Input to chip:** raw text resolves into avatar/name/remove chip.
- **Predictive suggestion lane:** suggestions above input; Tab cycles, Enter accepts/sends, ArrowRight accepts first at cursor end.
- **Transparent amount input:** animated digits under native transparent input for money/amounts.
- **Trailing action swap:** empty input shows passive tools; text input shows send.

## Numeric And Time Controls

- **Measuring-tape selector:** fixed center marker, moving ticks, low elasticity, snap on release.
- **Tick scrub slider:** dense ticks with floating value bubble for discrete numeric targets.
- **Waveform scrub:** inactive waveform base, clipped active foreground, needle playhead.
- **Linear progress inside spring UI:** time fills are linear; surrounding layout may spring.

## Feedback And Status

- **Retryable inline error:** status pill plus retry button; loading replaces error in same pill.
- **Rating then explain:** thumb up/down first, optional text second.
- **Copy confirmation in place:** button text changes to copied state; no toast needed.
- **Success as return path:** done state can also reset or repeat if that is the next expected action.

## Calendar And Navigation

- **Horizontal calendar rail:** nearby dates in a draggable strip; selected date drives detail panel.
- **Floating reading index:** collapsed progress ring + percentage; expanded topic list via portal.
- **Inline pagination:** previous/current/next for bounded content; no wrap.
- **Carousel/step wrap:** wrap only when content is cyclic or exploratory.

## AI And Prompt Surfaces

- **Modeful prompt input:** one field, selected AI mode/agent visible before send.
- **Agent icon strip:** compact model/provider selector when icons are recognizable.
- **Prompt footer controls:** secondary output type/settings below main input, opposite send.
- **Contextual AI bar:** tool rail switches into prompt input when AI refinement is active.

## Cards And Widgets

- **Metric-first fitness card:** giant number, tactile selector, bottom CTA.
- **Two-field currency swap:** editable source/destination fields, compact currency pickers, muted rate footer.
- **Voice note lifecycle:** idle mic, recording, review/playback, send/cancel in one control cluster.
- **Event reminder stack:** rows with type, amount stepper, unit cycle, remove.

## NEVER

- Never use a modal when a morphing disclosure or inline panel keeps context better.
- Never show all controls at once if the interaction has clear modes.
- Never wrap bounded data unless it is conceptually cyclic.
- Never leave an accepted value looking like raw input; resolve it into state, chip, or committed summary.
