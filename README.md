# Theorist

Maintain a continuously updated operating theory for ongoing engineering work.

`theorist` is an agent skill (Codex and Claude compatible) that keeps a per-repo narrative document at
`THEORY.MD` (repo root). The document explains the problem thesis, the current
system model, why the strategy is shaped the way it is, and where uncertainty
still exists.

It is intentionally not a task plan, changelog, or status report.

## Install

Use a skills directory for your client and clone into it:

```bash
SKILLS_DIR="${CODEX_SKILLS_DIR:-${CLAUDE_SKILLS_DIR:-$HOME/.codex/skills}}"
mkdir -p "$SKILLS_DIR"
git clone https://github.com/blader/theorist.git "$SKILLS_DIR/theorist"
```

If you already have the repo checked out, copy just the skill file:

```bash
mkdir -p "$SKILLS_DIR/theorist"
cp SKILL.md "$SKILLS_DIR/theorist/"
```

## Usage

Invoke it using your client's skill command.

Or ask naturally:

- "Keep the operating theory updated while you work."
- "Rewrite the theory doc based on what we just learned."
- "What changed in our theory after this debugging pivot?"

## What it enforces

- One theory doc per repo at `THEORY.MD` (repo root)
- Always-on activation in every substantive session
- Sticky activation: once active, it stays active for the full session
- Holistic rewrites (not appended logs)
- Clear separation between:
  - problem thesis,
  - operating theory,
  - strategy,
  - key discoveries/pivots,
  - open questions.
- Frequent in-session updates as learnings arrive (especially after
  investigate/implement/verify loops and verification outcomes).
- Updates when understanding changes, not when code churn happens.

## Why this helps

Most agent workflows optimize for local task completion. `theorist` adds a
lightweight strategic memory layer so future decisions remain coherent with the
latest mental model of the system.

## Files

- `SKILL.md`: canonical skill behavior and writing standard

## License

MIT
