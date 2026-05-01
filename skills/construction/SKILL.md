---
name: "butter-construction"
description: "Use when implementing Butter UI so React/Tailwind code produces premium motion, animated values, stable layout, accessible controls, and high-quality visual output fast."
---

# Butter Construction

## CORE DIRECTIVE: IMPLEMENT THE QUALITY, DO NOT DOCUMENT IT

Butter is only successful when the code visibly improves the UI. Do not leave
motion or polish as a TODO. Build the animation, stable dimensions, and visual
state language into the component.

When touching UI:
- add or improve motion
- stabilize dimensions
- animate changing text/numbers
- improve spacing/radius/type
- remove generic card/default styling
- keep code simple enough to ship quickly

## Required Implementation Defaults

- Use `motion/react` for layout, presence, active pills, text bloom, number transitions, drag.
- Use Tailwind for all static styling.
- Use shadcn tokens when available: `bg-background`, `bg-muted`, `text-foreground`, `border-border`.
- Use `lucide-react` for common UI icons; use other icon packs only for branded/category icons.
- Use local finite modes for compact widgets: `idle`, `open`, `editing`, `recording`, `reviewing`, `playing`, `sent`.
- Prefer one component with modeful geometry over many unrelated panels.

## Animated Text Primitive

Any changing short label should use this behavior:

- split into chars
- preserve spaces as `\u00A0`
- `AnimatePresence mode="popLayout" initial={false}`
- initial `{ opacity: 0, y: 10, scale: 0.5, filter: 'blur(2px)' }`
- animate `{ opacity: 1, y: 0, scale: 1, filter: 'blur(0px)' }`
- exit `{ opacity: 0, y: -10, scale: 0.5, filter: 'blur(2px)' }`
- spring `stiffness 200-240`, `damping 16-20`, `mass 1.2`
- delay `0.014 * index`; use `0.03 * index` for state headlines

Use for selected labels, copied/sent text, mode names, tab labels, compact headings.

Implementation shape:

```tsx
function AnimatedText({ value }: { value: string }) {
  return (
    <span className="inline-flex tabular-nums">
      <AnimatePresence mode="popLayout" initial={false}>
        <motion.span key={value} className="inline-flex">
          {value.split('').map((char, index) => (
            <motion.span
              key={`${char}-${index}`}
              initial={{ opacity: 0, y: 10, scale: 0.5, filter: 'blur(2px)' }}
              animate={{ opacity: 1, y: 0, scale: 1, filter: 'blur(0px)' }}
              exit={{ opacity: 0, y: -10, scale: 0.5, filter: 'blur(2px)' }}
              transition={{
                type: 'spring',
                stiffness: 240,
                damping: 16,
                mass: 1.2,
                delay: index * 0.014,
              }}
            >
              {char === ' ' ? '\u00A0' : char}
            </motion.span>
          ))}
        </motion.span>
      </AnimatePresence>
    </span>
  );
}
```

## Animated Number Primitive

Any changing number should use:

- tabular numerals
- fixed digit columns (`1ch` or explicit width)
- previous value ref to determine direction
- increasing: y `8/20 -> 0`, exit `-8/-20`
- decreasing: y `-8/-20 -> 0`, exit `8/20`
- opacity `0 -> 1`, scale `0.5 -> 1`, blur `2px -> 0`
- stable decimals for currency/metrics

Use for prices, timers, page numbers, percentages, distances, counters, ratings.

Implementation shape:

```tsx
function AnimatedDigit({ digit, direction }: { digit: string; direction: 1 | -1 }) {
  return (
    <span className="relative inline-flex w-[1ch] justify-center overflow-hidden tabular-nums">
      <AnimatePresence mode="popLayout" initial={false} custom={direction}>
        <motion.span
          key={digit}
          custom={direction}
          initial={{ y: direction > 0 ? 20 : -20, opacity: 0, scale: 0.5, filter: 'blur(2px)' }}
          animate={{ y: 0, opacity: 1, scale: 1, filter: 'blur(0px)' }}
          exit={{ y: direction > 0 ? -20 : 20, opacity: 0, scale: 0.5, filter: 'blur(2px)' }}
          transition={{ type: 'spring', stiffness: 200, damping: 16, mass: 1.2 }}
        >
          {digit}
        </motion.span>
      </AnimatePresence>
    </span>
  );
}
```

## Layout And Morphing

- Use shared `layoutId` for active pills, selected dates, selected tabs, trigger-to-panel morphs.
- Use measured height for dynamic expanded panels.
- Use `AnimatePresence` for open/close, rows, icons, labels, and feedback.
- Keep trigger and expanded object in the same visual family: radius, border, background, placement.
- Use portals only for fixed floating UI that must escape scroll/stacking contexts.
- Gate portals behind mounted state.

## Stable Dimensions

- Touch targets: `44-56px`.
- Icon buttons and action buttons: `shrink-0`.
- Numeric columns: fixed width.
- Tabs/options: stable padding and height.
- Scroll panels: fixed max height plus bottom fade.
- Mobile width: `max-w-[calc(100vw-32px)]`; expanded search can use `w-[calc(100vw-80px)]`.

## State And Data

- Derive display values from one source: selected option, active page, amount, rate, duration, scroll progress.
- Avoid duplicate derived state unless editing inverse values.
- Numeric input regex: `/^\d*\.?\d*$/`.
- Currency conversion goes through a shared base rate.
- Dates use ISO keys.
- Random-looking visual bars/ticks are generated once, not every render.

## Interaction Contracts

- Outside click closes lightweight floating controls.
- Single-choice popovers close on select.
- Enter triggers the visible primary action.
- Escape/clear returns to neutral state when low-risk.
- Confirm/check is for dependent temporary choices.
- Disabled controls suppress lively animation.

## Accessibility

- Clickable indicators are buttons.
- Use `aria-expanded` for disclosures.
- Use `role="menu"` for compact option shelves.
- Icon-only buttons need label/title.
- Disabled visuals match disabled behavior.

## Timers And Cleanup

- Clear intervals on mode exit and unmount.
- Copy/loading states use timeout cleanup.
- Recording duration and playback countdown are separate.
- Resize/scroll/document listeners are removed.
- Time/progress animation is linear, never spring.

## Final Implementation Check

Before finishing:
- There is real implemented motion, not just static styling.
- Changing short text uses the text bloom primitive.
- Changing numbers use the number primitive or NumberFlow-style motion.
- Active selection uses shared layout motion.
- Expanded UI morphs from its trigger.
- No text overflows.
- No generic low-quality default UI remains in touched surfaces.
