# Rational AI Orchestration

> A decision framework for using multiple AI models **without overspending** —
> free local models by default, paid APIs only when a concrete reason justifies
> the cost, and cross-model review as a quality mechanism.

**🇬🇧 English** · [🇵🇱 Polski](./README.pl.md)

---

## The problem

Most people pay for AI the way they'd pay for electricity if every light in the
house ran on a separate metered premium circuit: by default, without a system,
reaching for the most powerful (and most expensive) model for every task —
including the trivial ones.

It works. It's also wasteful. A large share of day-to-day AI work — translation,
summarization, classification, drafting, code review — runs perfectly well on
free local models. The expensive frontier models earn their cost on a *minority*
of tasks. The problem is almost never capability. It's the absence of a rule for
**when** the expensive option is actually warranted.

## The promise

This repository is not a tool and not a product. It's a **methodology** — a way
of thinking about AI cost as a first-class design constraint, written down so you
can adapt it to your own setup:

- **Local-first philosophy** — why "free by default, paid for a reason" is the
  right default, not a compromise.
- **A delegation map** — which *class* of task goes to which *class* of model.
- **Escalation rules** — a decision frame for when paying for a frontier or
  long-context API is genuinely worth it (with example thresholds you adjust to
  your own context).
- **Cross-model review** — how and why to confront 2–3 independent models, and —
  just as important — the **limits** of that technique.
- **Cost lessons** — recurring classes of expensive mistakes and the rules that
  prevent them.

## Who this is for

Practitioners who already use AI models seriously and want a *system* for it:
independent consultants, developers, technical founders, AI engineers. If you've
ever looked at an API bill and thought "most of this didn't need the premium
model" — this is for you.

It is **not** a beginner's "intro to LLMs", and it is **not** vendor marketing.
There are no affiliate links and no "best model" rankings. Model names and prices
change monthly; principles don't. This document deliberately talks about *classes*
of model and *relative* cost, not specific products.

## How to read it

Start with philosophy, then the delegation map. The rest can be read in any order.

| # | Document | What it gives you |
|---|----------|-------------------|
| 01 | [Philosophy](./docs/en/01-philosophy.md) | Why cost is a first-class design constraint; the "free by default" principle |
| 02 | [Delegation map](./docs/en/02-delegation-map.md) | Task class → model class mapping |
| 03 | [Escalation rules](./docs/en/03-escalation-rules.md) | A decision frame for when to pay for an API |
| 04 | [Cross-model review](./docs/en/04-cross-model-review.md) | The 2–3 model confrontation pattern — and its limits |
| 05 | [Cost lessons](./docs/en/05-cost-lessons.md) | Classes of expensive mistakes and preventive rules |

## A note on honesty

Two principles run through everything here:

1. **Relative, not absolute.** No prices, no token counts, no "this model is
   best." Those rot. Ratios and rules-of-thumb survive.
2. **No hype.** Where a technique has limits — and cross-model review has real
   ones — this document says so plainly. A method you can trust is one that tells
   you where it breaks.

## License

Documentation in this repository is licensed under
[CC BY 4.0](./LICENSE) — share and adapt with attribution.

## Author

By **Dariusz Ciesielski**. This is a personal, working methodology shared in the
open. Use it, adapt it, disagree with it — and adjust every example value to your
own context.
