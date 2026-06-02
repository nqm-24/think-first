# think-first

**Clarify → Grill → Plan → Execute.** A structured Claude Code skill that prevents premature execution on ambiguous requirements.

Inspired by [grill-me](https://github.com/mattpocock/skills) by Matt Pocock, enhanced with a clarification gate, PLAN.md generation, and clean-context handoff workflow.

## What it does

1. **Clarification Gate** — Before anything, check if the request is clear enough. If not, ask 3-6 essential questions.
2. **Socratic Grill** — Walk down every branch of the design tree, one question at a time.
3. **PLAN.md** — Consolidate the shared understanding into a structured plan.
4. **Clean-Context Handoff** — Guide the user to `/clear` and execute with fresh context.

## Install

### Via npx (recommended)

```bash
npx skills@latest add nqm-24/think-first
```

### Manual

Copy `skills/think-first/SKILL.md` into your Claude Code skills directory:

```bash
mkdir -p ~/.claude/skills/think-first
cp skills/think-first/SKILL.md ~/.claude/skills/think-first/
```

## Usage

```
/think-first
```

Then describe what you want to build, fix, or design. The skill will grill you until the requirement is crystal clear.

## License

MIT