---
name: "butter-patterns"
description: "Use when selecting premium Butter interaction patterns for controls, tabs, prompt bars, pickers, cards, widgets, feedback states, animated values, and compact app surfaces."
---

# Butter Patterns

## CORE DIRECTIVE: PICK A BETTER INTERACTION, NOT A DEFAULT COMPONENT

When implementing Butter, do not reach for generic dropdown/card/modal first.
Choose the pattern that makes the UI feel compact, tactile, animated, and fast.

Every pattern below expects:
- shared layout motion for active states
- Butter text/number animation for changing labels/values
- stable dimensions
- compact high-quality visual treatment
- no explanatory helper copy unless product-critical

## Pattern Selection Engine

Choose the strongest match:

- Need 2-4 choices visible at once -> horizontal option shelf or shared active pill tabs.
- Need one compact setting with dependent subchoices -> summary-to-editor.
- Need a tiny mode switch -> cycle button.
- Need changing numeric value -> animated number + fixed digit columns.
- Need user to scrub value -> tick scrubber or measuring tape selector.
- Need quick AI/project input -> modeful prompt bar.
- Need status + retry -> inline status pill with retry slide-in.
- Need copy/share -> morphing QR/copy panel, no toast.
- Need calendar/date browsing -> horizontal rail + detail panel.

## Mandatory Micro-Patterns

Use these everywhere they fit:

- **Animated label bloom:** selected labels, copied text, app type labels, mode names.
- **Animated number columns:** pages, prices, timers, percentages, miles, counts.
- **Shared active pill:** tabs, categories, options, selected day, frequency type.
- **Trigger morph:** collapsed button grows into input/panel/editor.
- **Trailing action swap:** empty input shows passive tools; non-empty input shows send.
- **Bottom fade:** scrollable detail panels fade out, no heavy scrollbar.

## Morphing Controls

- **Button becomes field:** one short input tied to a primary action.
- **QR reveal:** compact label button morphs to measured QR card, copy/close row below.
- **Search-or-browse bar:** search icon expands, categories yield, close restores browse.
- **Summary-to-editor:** compact setting display opens into structured choices, check commits.
- **Icon-to-agent input:** selected AI icon remains visible while input grows around it.

## Compact Selection

- **Shared active pill tabs:** icon+label, moving background, stable tab dimensions.
- **Horizontal option shelf:** 2-3 choices above trigger; selection closes immediately.
- **Cycle button:** tiny obvious sets such as Web/Mobile, day/week, unit/type.
- **Dot-to-icon step pager:** inactive dots, active icon, animated label above.
- **Frequency editor:** closed summary, open tab rail + dependent subgrid.

## Numeric And Time Controls

- **Animated page counter:** current page rolls; "of N" remains stable.
- **Currency input overlay:** animated digits below transparent native input.
- **Measuring-tape selector:** fixed center marker, moving ticks, low elasticity.
- **Tick scrub slider:** floating value bubble, snap to tick, lifted while dragging.
- **Voice note lifecycle:** mic -> waveform -> review timer -> send/cancel in one cluster.
- **Linear progress in spring shell:** progress linear, shell tactile.

## Prompt And AI Surfaces

- **Modeful prompt input:** one field, selected agent/model visible before send.
- **Agent icon strip:** compact recognisable provider selector.
- **Prompt footer controls:** type/settings below main input, send anchored right.
- **Context chip field:** raw text resolves into avatar/name/remove chip.
- **Predictive lane:** suggestions above input, Enter accepts/sends.

## Cards And Widgets

- **Metric-first card:** giant animated metric, secondary unit label, tactile selector, bottom CTA.
- **Currency swap card:** two animated numeric fields, compact currency pickers, muted rate footer.
- **Calendar widget:** horizontal date rail, selected date morph, detail panel with bottom fade.
- **Run widget:** large NumberFlow metric, draggable ruler, grounded CTA.
- **Feedback card:** rating first, optional explanation second, success returns to next action.

## NEVER

- Never use a static shadcn card when a compact object pattern fits.
- Never use a modal when morphing disclosure preserves context.
- Never show all controls at once if modes can reduce clutter.
- Never leave accepted input raw; resolve into chip, committed summary, or selected state.
- Never let a selected value change without text/number animation.
