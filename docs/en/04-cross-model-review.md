# 04 · Cross-model review: the pattern and its limits

[🇵🇱 Polski](../pl/04-cross-model-review.md) · [↑ README](../../README.md)

---

Cross-model review is the quality mechanism that pairs with cost discipline: since
your default is cheaper models, you want a cheap way to catch their mistakes — and
the cheapest is to ask *another* model. This document explains the pattern, and
then spends equal time on where it **doesn't** work, because a technique you trust
blindly is more dangerous than one you don't use.

## The pattern

> Confront **2–3 independent models** with the same plan, decision, or diff. Keep
> only what survives the confrontation.

Concretely:

1. **Produce the artifact** — a plan, an architecture decision, a code change.
2. **Send it to two independent reviewers** — by default, two *free local* models
   with different characters (e.g. one reasoning-heavy, one code-tuned). Two free
   perspectives cost nothing but a little time.
3. **Read the disagreements, not the agreements.** Where reviewers agree, you
   learn little. Where they *conflict*, you've found the load-bearing assumption.
4. **Escalate only on real deadlock** — if the two genuinely conflict or both are
   unsure, *then* a paid third opinion earns its cost (see
   [escalation rules](./03-escalation-rules.md)).
5. **Keep only what survives.** A finding that one model raises and the artifact
   can't defend is a finding to act on.

### Why independence matters

The value comes from the reviewers being *different* — different training, different
character, different failure modes. Two runs of the same model at the same settings
mostly agree with themselves; that's confirmation, not review. Diversity of
reviewer is the entire source of signal.

### A useful variant: adversarial review

Instead of "review this," prompt the reviewer to *attack* it: "find the strongest
reason this plan fails." Default the reviewer toward refutation. It's much harder
for a flawed plan to survive three independent attempts to break it than three
polite "looks good"s. When the stakes justify it, give each adversary a distinct
lens — correctness, security, "does this even reproduce" — so they fail the
artifact in different ways rather than redundantly.

## The limits — read this part twice

Cross-model review is a **quality** mechanism. It is **not** a security mechanism,
and treating it as one is a real mistake. Three hard limits:

### 1. Shared blind spots

Models trained on overlapping data share overlapping blind spots. If a mistake is
common in the training distribution — a popular-but-wrong idiom, a widespread
misconception — *every* model may repeat it confidently. Three reviewers that all
inherited the same blind spot will all miss the same thing and call it consensus.
**Agreement is not correctness.** It can just be shared ignorance.

### 2. It cannot catch what it cannot see

Cross-model review reads what you show it. It does **not** detect:

- **Secrets / leaked credentials** — a model reviewing your text won't reliably
  flag a leaked key, and you must never rely on it to. That's the job of
  deterministic tools (secret scanners), not an LLM's judgment.
- **Sensitive data exposure** — whether a "lesson" deanonymizes a real person is a
  human and policy question, not something review consensus settles.

If you need a guarantee, you need a **deterministic gate** — a scanner, a regex, a
checklist — not a probabilistic opinion. LLM review is at best a soft second pair
of eyes *after* the hard gates pass, never a substitute for them.

### 3. Confident wrongness

A model can refute a *correct* finding as persuasively as it confirms a wrong one.
Adversarial review reduces false positives but introduces false negatives:
sometimes the plan was right and the adversary's objection is the flawed one. The
output of review is *input to your judgment*, not a verdict that replaces it.

## The honest summary

Cross-model review is excellent at what it's good at: surfacing assumptions,
catching reasoning gaps, pressure-testing plans cheaply before you commit. It is
worthless — worse, dangerous — when asked to guarantee safety properties it
structurally cannot. Use it for quality. Use deterministic gates for security. Keep
the line between them bright.

The reason this document spends as long on the limits as on the pattern is itself
the point: **a method is trustworthy in proportion to how clearly it tells you
where it breaks.** Anyone selling you cross-model review as a safety net is selling
theater.

## Where to go next

- [Cost lessons](./05-cost-lessons.md) — recurring mistakes, including ones review
  would *not* have caught.
- [Escalation rules](./03-escalation-rules.md) — when the third opinion is worth
  paying for.
