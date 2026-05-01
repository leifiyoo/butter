# Butter

Butter is a compact UI design skill for AI coding agents. It captures a premium React/Tailwind/shadcn interaction language: soft physical objects, restrained neutral surfaces, stateful color, precise morphing motion, animated text/numbers, dense utility widgets, and strict anti-generic design rules.

Butter's core job is to make touched UI visibly better: smoother motion, better
spacing, stronger hierarchy, animated values, tactile controls, and fast
high-quality implementation.

It is intentionally opinionated but not one-note. The skill includes variation
systems for shape, surface, density, accent, and motion signature, plus an
unknown-element protocol for making unfamiliar UI high quality without ignoring
the user's request.

## Canonical Skill Files

- `skills/butter/SKILL.md` - root trigger, load order, core taste, quality gate
- `skills/butter-visual/SKILL.md` - radius, color, typography, spacing, surfaces
- `skills/butter-motion/SKILL.md` - springs, morphs, progress timing, text motion
- `skills/butter-patterns/SKILL.md` - reusable Butter component patterns
- `skills/butter-construction/SKILL.md` - implementation rules that protect design quality

## Download Choices

The repo intentionally exposes multiple skill entries so installers can choose
what to download:

- Default install:

  ```bash
  npx skills add leifiyoo/butter
  ```

- Install `skills/butter/SKILL.md` for one complete Butter command.
- Install `skills/butter-visual/SKILL.md`, `skills/butter-motion/SKILL.md`,
  `skills/butter-patterns/SKILL.md`, or `skills/butter-construction/SKILL.md` when you want
  only a focused part.
- Install all five only if you want separate slash commands for each Butter
  area.

If duplicate slash commands are annoying, install only the core Butter skill.

Best default: install `skills/butter/SKILL.md`. It tells agents to load the subskills
when real UI work needs deeper visual, motion, pattern, or construction rules.

## Agent Support

The repository includes adapters for common coding agents:

- Codex and other `AGENTS.md` readers
- Claude Code via `CLAUDE.md`
- GitHub Copilot via `.github/copilot-instructions.md`
- Kilo Code via `.kilo/rules/butter.md` and `.kilocode/rules/butter.md`
- Cursor via `.cursor/rules/butter.mdc`
- Windsurf via `.windsurf/rules/butter.md` and `.windsurfrules`
- Gemini via `GEMINI.md`
- Cline and Roo via `.clinerules` and `.roo/rules/butter.md`

Agent-specific files are intentionally short. The canonical Butter rules stay in `skills/`.
