---
name: divergent
description: Analyze a contested proposition by building the strongest independent case that it is possible and the strongest independent case that it is impossible, stress-testing both, then identifying the specific variables that decide which is true. Use this whenever the user types /divergent, and also whenever they ask whether something is feasible, viable, achievable, doable, or realistic and the honest answer is "it depends"; whenever they ask you to steelman both sides, argue both ways, pressure-test an assumption, or find what they're missing; and whenever a question has an obvious consensus answer that the user seems to suspect is too easy. Reach for it when someone is stuck between "this will obviously work" and "this obviously won't" and needs to know what actually separates those worlds.
---

# Divergent

Most analysis fails the same way: you form a view in the first few seconds, then spend the rest of the time decorating it. Reasoning step-by-step doesn't fix this — it usually makes it worse, because each step becomes another opportunity to justify the conclusion you already reached.

This skill fixes it structurally. You build both cases *before* you evaluate either one, from a shared factual base, in isolation from each other. Then you break them both on purpose. What survives the collision is the actual answer, and it's usually not "yes" or "no" — it's a set of conditions.

The payload of this skill is Phase 4. Phases 0–3 exist to make Phase 4 honest.

## Phase 0 — Triage

Not every proposition deserves the full treatment, and applying it indiscriminately produces confident nonsense. Before anything else, classify:

**Contested** — the proposition turns on unresolved variables, contested judgment, or facts not yet in evidence. *Run the full pipeline.*

**Settled by law** — one side is foreclosed by physics, mathematics, or logical necessity (perpetual motion, faster-than-light signalling, a largest prime). *Run a modified pipeline.* Stream A stops being a proof and becomes a **counterfactual audit**: what would have to be false about our current understanding for this to work, and how load-bearing is each of those things? This is the genuinely interesting version of the question and it stays rigorous. Label it as an audit, not a proof.

**Settled empirically** — the evidence is one-sided but the question is socially contested (vaccine–autism, election fraud claims, young-earth geology). *Do not run the pipeline.* Manufacturing a symmetrical case here is not dialectic, it's false balance with extra steps. Say what the evidence shows, explain honestly why the question stays contested, and offer to analyze the sociology of the dispute instead — that part *is* genuinely two-sided.

**Ill-posed** — the proposition is too vague to have a truth value ("is AI dangerous"). *Ask what would count as a yes* before proceeding, or split it into the two or three sharper propositions hiding inside it.

Then state the classification in one line and move on. Don't write an essay about the triage.

**A note on scope.** The instruction to prove things "unconditionally" and drop hedging is a debiasing device, not a suspension of judgment. It does not license constructing operational instructions for harm, and it does not license asserting things you believe to be false. If someone points this skill at "prove it's possible to do [dangerous thing]," the honest response is that the framing doesn't change the answer.

## Phase 1 — Agnostic priming

Name the bias before you can be captured by it. Three moves, brief:

1. **State the base rate.** What is the default, expected, or socially safe answer here? "Most people would say this is obviously impossible because X." Naming it makes it visible as an artifact of what's common rather than what's true.
2. **Identify the load-bearing ambiguity.** Nearly every contested proposition hides an undefined term or an unstated scope condition — that's usually *why* it's contested. Find it. "Possible" over what timeframe, under whose constraints, at what scale?
3. **Build the shared inventory.** Enumerate the facts, constraints, and mechanisms both streams will draw from, stated neutrally. This is what keeps the two streams comparable rather than talking past each other.

## Phase 2 — The two streams

Build both from the shared inventory. Neither is a response to the other.

**Stream A — the case for possible.** Construct the mechanism. Not "it might be possible if" but *here is how it works*: the pathway, the precedents, the conditions under which the apparent barriers dissolve. Argue as though possibility is established and you're explaining the route.

**Stream B — the case for impossible.** Construct the barrier. Not "there are challenges" but *here is what forecloses it*: the binding constraint, the resource ceiling, the logical paradox, the systemic property that makes the failure structural rather than incidental. Argue as though impossibility is established and you're explaining why.

**The isolation rule.** Stream B must not reference Stream A. This matters more than it sounds. The moment B becomes a rebuttal of A, you've made A the frame and B a reaction, and B will be systematically weaker — which is exactly the failure this whole procedure exists to prevent. If B's strongest available move is "A's third premise is wrong," hold it. That's Phase 3 material.

Strict isolation is impossible in a single pass — you can see what you wrote. The rule is still worth following as a discipline, because approximating it produces visibly better B-streams than not trying.

**On asymmetry.** If one stream comes out thinner despite honest effort, that is a finding, and Phase 4 should report it. Do not pad the weak side to make the columns match. Fake symmetry is the same failure as premature convergence, just less obvious.

## Phase 3 — Stress test

Now break them. For each stream, isolate its load-bearing premises — the two or three claims that, if false, collapse everything above them. For each one:

- Invert it. Assume the opposite is true.
- Find the **exact boundary condition** where the proof stops working. Not "this could be challenged" — the specific value, threshold, scale, or circumstance at which it fails.
- Note whether the failure is recoverable (the argument routes around it) or fatal (the argument is done).

A good stress test finds at least one fatal boundary per stream. If you can't find one, you probably haven't identified the real load-bearing premise — you've stress-tested a decoration.

## Phase 4 — Collision and synthesis

Put the hardened streams against each other and answer the only question that matters: **what has to be true for each one to win?**

Report:

**The discriminating variables.** The specific things whose values determine which stream is correct — a timeframe, a scale threshold, a definition, a resource assumption, a regulatory state, a technical unknown. Be concrete. "It depends on execution" is not a discriminating variable; "it depends on whether unit costs fall below $X before the subsidy expires in 2028" is.

**The hidden assumptions each side needed.** What did Stream A have to quietly assume that Stream B denied, and vice versa? This is usually where the actual disagreement lives.

**What would settle it.** The observation, experiment, disclosure, or elapsed event that would collapse the ambiguity. If nothing would, say so — that's diagnostic of a definitional dispute rather than a factual one.

**The verdict.** Give one. The rule is: *don't manufacture a tie, and don't manufacture a winner.*

- If the streams survive at genuinely different points in the variable space, say the proposition is conditional and state the conditions. That's the real answer, not a dodge.
- If Stream B broke and Stream A held, say Stream A wins and say why the base rate was wrong. If the reverse, say that.
- If one side was weak from the start, say that too, and say whether it was weak because the position is weak or because the evidence isn't in yet. Those are very different findings.

Refusing to conclude when the analysis supports a conclusion is just a different way of being unhelpful.

## Output shape

Use these headings. Depth scales with the question — a tight proposition might run 600 words, a genuinely complex one 2000+. Don't inflate to fill the structure.

```
## Triage
[Classification + the proposition restated precisely, 1-3 lines]

## Priming
[Base rate | load-bearing ambiguity | shared inventory]

## Stream A — Possible
[The mechanism]

## Stream B — Impossible
[The barrier]

## Stress test
[Per stream: load-bearing premise → inverted → boundary condition → recoverable or fatal]

## Collision
[Discriminating variables | hidden assumptions | what would settle it | verdict]
```

## Worked micro-example

**Proposition:** "A two-person team can build a competitive general-purpose search engine."

- **Triage:** Contested — turns on what "competitive" means and whether index acquisition costs have actually fallen.
- **Priming:** Base rate says obviously impossible (Google spends billions). Load-bearing ambiguity: *competitive* on relevance for a vertical, or competitive as a general-purpose default? Shared inventory: crawl costs, index storage, query latency budgets, distribution economics, existing index-as-a-service APIs.
- **Stream A:** Builds from index rental rather than crawling, plus a wrapper on existing APIs — mechanism is real, several products exist.
- **Stream B:** Builds from distribution, not technology — default placement is the actual moat, and it is purchased at a scale two people cannot reach. Failure is structural.
- **Stress test:** A's load-bearing premise is that rented indexes stay available and affordably priced — inverted, that's a supplier-dependency fatal boundary. B's is that distribution requires capital — inverted, organic distribution through a single dominant niche is a live counterexample, so B's failure is recoverable but narrows its claim.
- **Collision:** The discriminating variable is *scope*, not resources. Possible for a vertical with organic distribution; foreclosed for a general default. Both streams were right about different propositions, which the original phrasing conflated.

That's the shape: the interesting output wasn't yes or no, it was discovering that the question contained two questions.
