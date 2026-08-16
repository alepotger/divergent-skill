# divergent

A Claude Skill for analyzing contested propositions without prematurely collapsing to one answer.

Most reasoning fails the same way: a view forms in the first few seconds, and everything after that is decoration. `/divergent` fixes this structurally — it builds the strongest independent case *for* a proposition and the strongest independent case *against* it, from a shared factual base, before either one is evaluated. Then it stress-tests both on purpose and reports what's left standing.

The output usually isn't "yes" or "no." It's the specific set of conditions that decide which one is true — which is normally the actually useful answer.

## Install

1. Download [`divergent/SKILL.md`](./divergent) from this repo (or clone it).
2. Add it to Claude as a skill — via Claude.ai's skill upload, `claude-code`'s skills directory, or your org's skill catalog, depending on where you're using it.
3. Trigger it by typing `/divergent`, or just ask a question that fits (see below) — the skill also triggers automatically on feasibility questions where the honest answer is "it depends."

## What it does

The skill runs a five-phase pipeline:

| Phase | What happens |
|---|---|
| 0 — Triage | Classifies the proposition: genuinely contested, settled by physical/logical law, settled empirically but socially contested, or too vague to have a truth value. Each gets different treatment — the pipeline doesn't run at all for settled-empirical claims, since manufacturing a symmetrical case there is false balance, not dialectic. |
| 1 — Priming | States the base-rate assumption out loud, finds the ambiguous term the dispute is actually hiding behind, and builds a shared fact inventory. |
| 2 — Two streams | Builds the case *for* possible and the case *for* impossible independently — Stream B is not allowed to rebut Stream A. |
| 3 — Stress test | Breaks both streams on purpose, looking for the exact boundary condition where each argument's load-bearing premise fails. |
| 4 — Collision | Identifies the concrete variables that decide which stream wins, the hidden assumption each side needed, what evidence would settle it, and a real verdict — conditional, or a clear winner, not a manufactured tie. |

## Example

**Prompt:**
> /divergent A four-day work week (32 hours, same pay) is viable for a 500-person manufacturing company without lowering output.

**Output (abridged):**

```
## Triage
Contested — turns on whether output is bound by labor-hours or by machine/shift
throughput, which manufacturing (unlike knowledge work) makes a real question.

## Priming
Base rate: "obviously not — factories run on hours, not focus." Load-bearing
ambiguity: "without lowering output" could mean same total units, or same
units per labor-hour. Shared inventory: existing 4-day pilots are almost
all knowledge-work; manufacturing has hard machine-time and shift-coverage
constraints; overtime and fatigue-related defect data exist from prior
shift-length studies.

## Stream A — Possible
Output in manufacturing is often capped by machine throughput and shift
scheduling, not raw labor-hours — a compressed schedule with reorganized
shifts (e.g. four 10-hour days, staggered crews) can hold machine utilization
constant while cutting individual hours. Fatigue-linked defect rates tend to
rise in the last 1-2 hours of long shifts; trimming those specific hours may
recover some of the "lost" output through fewer errors and less rework.

## Stream B — Impossible
Manufacturing output is generally hour-bound in a way knowledge work isn't:
a machine that runs 8 hours produces roughly 8 hours of units, and there's
a hard floor on staffing needed to run each shift safely. Cutting scheduled
hours by 20% without adding a compensating shift or more machines removes
capacity that fatigue-reduction gains can't realistically offset at typical
manufacturing defect-rate baselines.

## Stress test
Stream A's load-bearing premise — fatigue-reduction gains offset lost hours —
holds only if current defect/rework rates are unusually high; inverted, a
already-lean, low-defect line has no slack to recover, which is a fatal
boundary for that specific case. Stream B's premise — output is strictly
hour-bound — holds only without a compensating shift; inverted, adding a
partial fifth crew restores capacity, which makes B's failure recoverable
rather than fatal, at added labor cost.

## Collision
Discriminating variables: current defect/rework rate (headroom for A) and
whether the company can add a partial shift (rescues B's objection at a
cost). Hidden assumption in A: there's inefficiency to recover. Hidden
assumption in B: headcount is fixed. What would settle it: a 90-day pilot
on one line with baseline defect-rate data already in hand.

Verdict: conditional, not close. High-defect, currently overtime-heavy
lines: viable. Already-lean, tightly-staffed lines: not viable without
added headcount, which changes the economics the proposition assumed away.
```

Full output includes the reasoning, not just the collapsed verdict — the abridged version above trims Stream A/B down for the README.

## When to reach for it

- Feasibility questions where "it depends" is the honest answer, but on what?
- Steelmanning both sides of something you or someone else already has a strong opinion on
- Questions with an easy consensus answer that you suspect is too easy
- Any "will X actually work" question before you commit resources to finding out the hard way

## When it won't (and shouldn't) give you a 50/50

The skill has a triage step precisely so it doesn't manufacture false balance. Ask it whether a perpetual motion machine is possible and it'll tell you no, flatly, and explain why pretending otherwise isn't rigor. Ask it something empirically settled but socially contested and it'll decline to build a symmetrical case, tell you what the evidence actually shows, and offer to analyze *why the dispute persists* instead — which is a genuinely different, two-sided question.

## License

MIT
