---
name: "butter"
description: "Use when designing, building, or reviewing Butter-style interfaces: compact premium React/Tailwind app UI with soft surfaces, morphing controls, precise motion, dense utility widgets, and strict anti-generic design rules."
---

# Butter

Butter is a compact interaction language for premium utility UI. It favors soft physical objects, restrained color, precise motion, and controls that morph instead of spawning new panels.

## Load What You Need

- Visual decisions: read `visual/SKILL.md`.
- Motion decisions: read `motion/SKILL.md`.
- Implementation decisions that affect design quality: read `construction/SKILL.md`.
- Pattern choice: read `patterns/SKILL.md`.
- For building a visible component or app screen, read all four files before implementing. The root file alone is only a router and taste checksum.
- For other AI agents, route them here first, then into the four subfiles. Do not duplicate or invent alternate Butter rules in agent-specific instruction files.

## Core Taste

- Neutral shell, strong geometry, low visual noise.
- Radius communicates state: connected groups share edges; active objects separate and regain full corners.
- Color is stateful, not decorative.
- Motion explains continuity: one object changing role.
- Dense controls are better than airy marketing cards.
- Typography is confident: semibold labels, bold actions, tabular numbers.

## Default Values

- Radius: `24-40px` for expressive capsules/cards, `8-12px` for shadcn-compatible utility variants.
- Borders: `1-2px`, soft neutral.
- Touch targets: `44-56px`.
- Text: `14-18px` controls, `20-30px` state labels, `56-84px` hero metrics.
- Springs: firm `400-600/35-50`, shared active pill `280-300/25-30`, text bloom `200-240/16-20`.
- Letter bloom: y `10`, scale `0.5`, blur `2px`, delay `0.014s`; headlines can use `0.03s`.

## Hard Rules

- NEVER build landing-page composition for a tool. Build the usable object first.
- NEVER add decorative blobs, generic gradients, or explanatory UI copy.
- NEVER let text overflow controls.
- NEVER animate time with springs.
- NEVER let expanded states look unrelated to their collapsed trigger.
- NEVER preserve implementation trivia in Butter guidance; keep only rules that change visual or motion decisions.

## Quality Gate

Before finishing Butter UI work, check: compact app object, stable dimensions, no nested cards, no generic hero/marketing layout, stateful color only, radius/border/surface values match Butter, tabular numbers where numeric, active objects morph from their trigger, time animations are linear, tactile motion uses Butter springs, touch targets are at least `44px`, and text fits on mobile.
