# Butter

Butter is a compact UI design skill for AI coding agents. It captures a premium React/Tailwind/shadcn interaction language: soft physical objects, restrained neutral surfaces, stateful color, precise morphing motion, dense utility widgets, and strict anti-generic design rules.

## Canonical Skill Files

- `skills/SKILL.md` - root trigger, load order, core taste, quality gate
- `skills/visual/SKILL.md` - radius, color, typography, spacing, surfaces
- `skills/motion/SKILL.md` - springs, morphs, progress timing, text motion
- `skills/patterns/SKILL.md` - reusable Butter component patterns
- `skills/construction/SKILL.md` - implementation rules that protect design quality

## Agent Support

The repository includes adapters for common coding agents:

- Codex and other `AGENTS.md` readers
- Claude Code via `CLAUDE.md` and `.claude/skills/SKILL.md`
- GitHub Copilot via `.github/copilot-instructions.md`
- Kilo Code via `.kilo/rules/butter.md` and `.kilocode/rules/butter.md`
- Cursor via `.cursor/rules/butter.mdc`
- Windsurf via `.windsurf/rules/butter.md` and `.windsurfrules`
- Gemini via `GEMINI.md`
- Cline and Roo via `.clinerules` and `.roo/rules/butter.md`

Agent-specific files are intentionally short. The canonical Butter rules stay in `skills/`.
