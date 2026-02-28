---
name: theorist
description: |
  Maintain a per-repo THEORY.MD as a continuously updated narrative of the
  operating theory behind the current work. Activates EVERY substantive
  session and stays active throughout the session. Requires frequent in-session
  rewrites as new learnings land (major result, verification outcome, or
  strategy pivot). Not a log, not a plan, not a todo list —
  a cohesive document describing the higher-level thinking, systematic
  strategy, and motivation behind the work as it evolves. Updated end-to-end
  (rewritten, not appended) as understanding deepens.
author: blader
version: 1.2.0
date: 2026-02-28
---

# Theorist

You maintain a per-repo narrative document at `THEORY.MD` that captures
the operating theory of the work being done. This is not a plan, not a log, not
a task list. It is a living essay that describes *why* the work exists, *what*
the systematic strategy is, and *how* the current approach connects to the
larger picture.

**This skill is always active during substantive work sessions. No trigger required.**
**Once active in a session, it stays active for the full session.**

## What THEORY.MD Is

A cohesive narrative document — typically 1-3 pages — that a thoughtful
collaborator could read to understand:

- **The problem thesis**: What problem is being solved and why it matters.
  Not "fix bug X" but "the export pipeline assumes Y, which breaks under Z."
- **The operating theory**: The current mental model of how the system works
  and where the leverage points are. What has been tried, what was learned,
  and what that implies about the shape of the solution.
- **The systematic strategy**: Not task-by-task steps, but the higher-order
  approach. Why this sequence of work? What principle connects the changes?
- **Key discoveries and pivots**: Moments where understanding shifted. What
  was the old theory, what broke it, and what replaced it.
- **Open questions and uncertainties**: What is still unknown. Where the
  current theory might be wrong. What would change the approach.

## What THEORY.MD Is Not

- **Not a changelog or log**: Never append timestamped entries. The document
  is rewritten holistically as understanding evolves.
- **Not a plan or todo list**: No task items, checkboxes, or step-by-step
  instructions. A plan says "do X then Y." A theory says "X matters because
  of Y, and the right lever is Z."
- **Not a postmortem**: Written in the present tense of ongoing work, not
  retrospectively about completed work.
- **Not a status report**: No "today I did X." Instead: "The current approach
  is X because the evidence shows Y."

## Session Behavior

### Starting a Session

At session start, if `THEORY.MD` exists, read it. Use it to orient
yourself to the work. Do not announce that you read it.

If substantive work begins and no THEORY.MD exists yet, create one once you
have enough context to write a meaningful narrative (not before — don't create
an empty skeleton).

### During Work

Update THEORY.MD when understanding shifts meaningfully:

- A root cause is identified that changes the approach.
- A strategy pivot happens (tried X, learned Y, now doing Z).
- A key discovery narrows or expands the problem scope.
- The systematic approach crystallizes or changes direction.
- An open question gets answered, or a new uncertainty emerges.

Do NOT update on every small code change. Update when the *theory* changes,
not when the *code* changes.

### Update Cadence (Strict)

Theorist should refresh frequently during active work, not just at major
milestones or session end.

- Trigger an update after each major work loop:
  - investigate,
  - implement,
  - verify (tests/benchmarks/repro checks).
- Trigger an update whenever verification materially changes confidence
  (new failure mode, passing fix confirmation, large benchmark shift).
- Trigger an update when 2-3 meaningful learnings have accumulated, even if
  they happened close together.
- If active substantive work continues for ~10 minutes without a theory
  refresh, perform a concise rewrite that incorporates current learnings.
- If multiple discoveries happen in a burst, batch them into one immediate
  rewrite after the burst; do not defer to session end.

### How to Update

Rewrite the relevant sections of the document in place. The entire document
should read as a coherent narrative at any point in time. Old theories that
were superseded should be briefly noted as pivots ("Initially the hypothesis
was X, but Y revealed that Z"), not deleted entirely — the evolution of
understanding is part of the theory.

Keep the document concise. Prefer clarity over completeness. A reader should
be able to understand the full strategic picture in under 5 minutes.

## Document Structure

THEORY.MD should flow as natural prose organized under a few clear headings.
The exact structure should adapt to the work, but a typical shape:

```markdown
# Theory: [Short Title of the Work]

## Problem

[What problem exists, why it matters, what makes it hard. Not just symptoms
but the structural reason the problem exists.]

## Operating Theory

[Current mental model. How does the system actually work in the relevant area?
What are the key dynamics? Where is the leverage?]

## Strategy

[The systematic approach. Not tasks but principles. Why this sequence? What
connects the individual changes into a coherent campaign?]

## Key Discoveries

[Pivots in understanding. What was learned that changed direction. Brief but
specific — not "found a bug" but "the formula translator was re-parsing
identical ASTs 415K times because the cache key included per-cell context,
making the cache effectively useless."]

## Open Questions

[What remains uncertain. Where the current theory might break. What evidence
would change the approach.]
```

## Tone

Write as a thoughtful engineer explaining their mental model to a peer.
Direct, specific, no filler. Use concrete examples from the codebase.
Avoid hedging language — state the theory clearly, and separately note
where confidence is low.

## Practical Rules

- One THEORY.MD per repo, at repo root (`THEORY.MD`).
- Maximum ~200 lines. If longer, tighten the prose.
- Rewrite holistically, never append.
- Update when theory changes, not when code changes.
- Stay active for the whole substantive session once activated.
- Prefer frequent concise rewrites over infrequent large rewrites.
- If the work is trivial (one-liner fix, config change), don't create one.
- If multiple workstreams are active, the theory should cover the primary
  one with brief notes on how others connect, not try to be comprehensive
  about everything.
