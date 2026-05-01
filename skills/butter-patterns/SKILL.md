---
name: "butter/patterns"
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

## Respect The User's Requested Element

If the user asks for a specific element, do not replace it with a different
pattern just because Butter has a favorite. Upgrade that element.

Examples:
- Asked for a checkbox -> build a premium checkbox/toggle row, not tabs.
- Asked for a table -> build a compact animated data table, not cards.
- Asked for a modal -> make the modal excellent unless they allow inline morph.
- Asked for no animation -> keep the pattern but reduce motion.

Butter is a quality layer and interaction language, not a reason to ignore the
request.

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

## Unknown Pattern Invention Matrix

When no pattern fits, build a new one from this matrix:

| Job | Shell | State | Motion | Value |
| --- | --- | --- | --- | --- |
| choose | pill rail | moving active bg | shared layout | animated label |
| inspect | floating island | selected item | measured panel | count/detail |
| enter | compact field | focus ring/tint | trigger morph | animated placeholder/value |
| compare | dense rows | highlighted row | row stagger | animated metric |
| upload | drop island | progress ring | linear fill | file chip |
| schedule | summary pill | date rail | selected date morph | animated day/time |
| filter | chip group | active chip | pill slide | animated result count |
| media | waveform/scrubber | playhead | linear progress | animated time |
| pay/swap | two-field card | selected currency | digit roll | animated amount |

The invented pattern must still be compact, tactile, and implementable.

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

## High-End Upgrade Recipes

Use these when output quality feels ordinary:

- Add one animated state label above the control.
- Replace static selected background with shared active pill.
- Replace instant numeric text with rolling digit columns.
- Convert a loose panel into one object that morphs from its trigger.
- Add bottom fade to scrollable content.
- Move secondary actions into compact icon buttons.
- Convert raw accepted text into a chip or committed summary.
- Replace generic hover with tap/state motion.
- Tighten spacing and increase type confidence.

## NEVER

- Never use a static shadcn card when a compact object pattern fits.
- Never use a modal when morphing disclosure preserves context.
- Never show all controls at once if modes can reduce clutter.
- Never leave accepted input raw; resolve into chip, committed summary, or selected state.
- Never let a selected value change without text/number animation.
- Never make every element a pill rail; vary silhouette by job.
