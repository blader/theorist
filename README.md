# Theorist

Maintain a continuously updated operating theory for ongoing engineering work.

`theorist` is a Codex/Claude skill that keeps a per-repo narrative document at
`.claude/THEORY.MD`. The document explains the problem thesis, the current
system model, why the strategy is shaped the way it is, and where uncertainty
still exists.

It is intentionally not a task plan, changelog, or status report.

## Install

### Codex

```bash
git clone https://github.com/blader/theorist.git ~/.codex/skills/theorist
```

### Claude Code

```bash
git clone https://github.com/blader/theorist.git ~/.claude/skills/theorist
```

## Usage

Invoke directly:

- Codex: `$theorist`
- Claude Code: `/theorist`

Or ask naturally:

- "Keep the operating theory updated while you work."
- "Rewrite the theory doc based on what we just learned."
- "What changed in our theory after this debugging pivot?"

## What it enforces

- One theory doc per repo at `.claude/THEORY.MD`
- Holistic rewrites (not appended logs)
- Clear separation between:
  - problem thesis,
  - operating theory,
  - strategy,
  - key discoveries/pivots,
  - open questions.
- Updates when understanding changes, not when code churn happens.

## Why this helps

Most agent workflows optimize for local task completion. `theorist` adds a
lightweight strategic memory layer so future decisions remain coherent with the
latest mental model of the system.

## Files

- `SKILL.md`: canonical skill behavior and writing standard

## License

MIT
