# 05 · Cost lessons: classes of expensive mistakes

[🇵🇱 Polski](../pl/05-cost-lessons.md) · [↑ README](../../README.md)

---

These are not war stories. Each lesson below is a **synthetic composite** — a
*class* of mistake assembled from the general shape of how things go wrong, not a
record of any one event, person, or project. The value is in the pattern and the
rule that prevents it, not in whose week it ruined. No dates, no amounts, no
names — because the lesson is the same regardless of those, and because the
specifics are nobody's business.

Read each as: *here is a way to waste money or quality, and here is the rule that
stops it.*

---

## Lesson 1 — The mechanism that cost more than the task

**The class of mistake.** A routine job — the kind a single cheap pass handles —
gets run through heavy machinery: an elaborate multi-agent orchestration, a
premium model fanned out across many parallel calls, a process far larger than the
problem. The work gets done, but at a cost wildly out of proportion to its
difficulty. Often the trigger is a word — "thorough", "max", "comprehensive" —
interpreted as "use the biggest possible apparatus" rather than "be careful."

**Why it happens.** Bigger feels safer and more diligent. Elaborate machinery
*looks* like rigor. And the cost is invisible at the moment of choosing — you see
the apparatus, not the invoice.

**The rule.** *Match the weight of the mechanism to the weight of the task.*
"Thorough" describes the **quality of the conclusion**, not the **size of the
apparatus** — you can be thorough with a light tool. Before reaching for
orchestration or a fanned-out premium fleet, ask whether a single sequential pass
on a cheap model reaches the same answer. Usually it does.

---

## Lesson 2 — Iterating without a baseline

**The class of mistake.** A working process gets "improved" over several rounds.
Each change looks locally reasonable. Nobody compares the new output against the
*old* output on the same inputs. Quality drifts downward, slowly, invisibly — and
because each step felt like progress, the regression is only discovered much later,
after the good version is hard to recover.

**Why it happens.** Internal metrics ("the score went up") decouple from the metric
that actually matters (does the result still do its job). You optimize the proxy
and lose the target. Without a frozen baseline to compare against, there's no
signal that you're going backwards.

**The rule.** *Establish a baseline before you reprocess anything at scale.* On a
small, fixed sample, compare the new version against the previous one — same
inputs, side by side. If the new version is meaningfully worse, stop and diagnose
*before* running the full batch. And keep one supreme metric that reflects real
success, not an internal proxy that can rise while the real thing falls.

---

## Lesson 3 — Building on an unverified claim

**The class of mistake.** A note from earlier — a prior diagnosis, a handoff, a
"we established that X" — gets treated as fact. A whole chain of reasoning, or a
cost calculation, gets built on top of it. The original claim was a *hypothesis at
the time it was written*, never re-checked. It was wrong. Everything built on it
inherits the error, and the error propagates through every downstream conclusion
until something finally contradicts reality.

**Why it happens.** Past notes carry false authority — they're written down, so
they feel settled. Re-verifying feels redundant. The cost of checking is small and
immediate; the cost of not checking is large and deferred, so the discount rate
fools you.

**The rule.** *Treat upstream claims as hypotheses, not ground truth — especially
your own past notes.* Before building on a remembered diagnosis, spend the small
amount of time to confirm it against current reality (read the actual state, run
the actual check). Numbers in a calculation each need a provenance: a source, an
explicit assumption, or a derivation from other sourced numbers. A figure with no
provenance is a guess wearing a suit.

---

## Lesson 4 — Paying for comfort

**The class of mistake.** The premium model gets chosen not because the task needs
it but because it *feels* better — safer, more serious, more diligent. No specific
capability of the cheaper model is found wanting; it's never even tried. Multiply
this across a month of small decisions and the bill is mostly comfort, not
capability.

**Why it happens.** The belief that "more powerful = better result" operates even
when you can't name what the difference would be. It's the default human reach for
the biggest available tool, and it's completely invisible per-decision — each
individual escalation seems harmless.

**The rule.** *If you can't name the specific thing the cheaper model would get
wrong, you're paying for comfort.* Make the cheap option the one that needs no
justification and the expensive one the exception that does. Run the five-second
test (see [escalation rules](./03-escalation-rules.md)) every time. Comfort is
real, but it isn't a reason.

---

## The thread connecting all four

Every lesson here is a variant of the same root cause: **a cost (in money or
quality) that was invisible at the moment of the decision.** The mechanism's price,
the slow drift, the unverified claim, the comfort premium — none of them announce
themselves when you choose. The entire methodology is a set of habits for making
those invisible costs *visible at decision time*: name the reason, check the
baseline, verify the claim, match the tool. Discipline isn't virtue here. It's just
moving the cost back to where you can see it before you pay it.

## Where to go next

- [Philosophy](./01-philosophy.md) — the principle these lessons defend.
- [Cross-model review](./04-cross-model-review.md) — and an honest note that review
  would *not* have caught most of these; they're discipline failures, not reasoning
  gaps.
