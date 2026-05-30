# 01 · Philosophy: free by default, paid for a reason

[🇵🇱 Polski](../pl/01-philosophy.md) · [↑ README](../../README.md)

---

## The core principle

> **Default to free local models. Escalate to paid APIs only for a concrete,
> nameable reason.**

That's the whole philosophy in one sentence. Everything else in this repository
is the machinery that makes the sentence operational: how to decide what "a
concrete reason" means, how to route work, and how to keep yourself honest about
the difference between *needing* the expensive model and merely *reaching* for it.

## Why cost is a first-class design constraint

In conventional software, you optimize for correctness first and cost later, if
at all — a function call is effectively free. AI inference breaks that intuition.
Every call to a frontier model has a non-trivial marginal price, and that price
varies by **one to two orders of magnitude** depending on which class of model
you choose for the same task.

When the cost difference between two ways of doing the same thing is that large,
cost stops being an afterthought and becomes a **design axis** — something you
decide deliberately at the moment of routing, not something you reconcile on a
monthly invoice. Treating it as first-class doesn't mean being cheap. It means
spending *on purpose*.

## Why "free by default" is a default, not a compromise

The instinct to reach for the most capable model "just to be safe" rests on a
hidden assumption: that the hard part of most tasks is capability. For the bulk
of everyday AI work, it isn't.

Consider what a typical day of practical AI use actually contains: translating a
message, summarizing a document, classifying inputs, extracting structured data,
drafting boilerplate, reviewing a small diff, answering a factual question you
already know the shape of. None of these stress the frontier of model capability.
A competent local model — one that runs on hardware you already own, at zero
marginal cost — handles them at a quality that is **indistinguishable in the
result that matters**.

So "free by default" is not the budget option you settle for. It's the *correct*
option for the task class, and the expensive model would be the one you'd have to
*justify*. The burden of proof runs the other way from how most people set it up.

### The "feels better" trap

The most expensive habit in AI use is not a pricing tier. It's the quiet belief
that a more powerful model gives a better result *even when you can't point to
why*. This is the single failure mode this whole methodology exists to counter.

A useful five-second test before escalating:

> *"Is this task genuinely hard or strategic — or is the premium model just more
> comfortable?"*

If you can't name the specific thing the cheaper model would get wrong, you are
paying for comfort, not capability. Comfort is a real human need. It is not a
reason to escalate.

## The shape of the rule

The philosophy resolves into a simple, asymmetric default:

- **Cheap/local is the assumed answer.** It needs no justification.
- **Expensive/paid is the exception.** It needs a reason from a short, explicit
  list (see [escalation rules](./03-escalation-rules.md)).
- **When in doubt, stay cheap.** Doubt is not a reason to escalate; it's a reason
  to try the cheap path first and *observe whether it actually fails*.

This asymmetry is the entire game. Most cost discipline is just refusing to let
"it might be better" function as a reason.

## What this philosophy is not

- **Not anti-frontier.** Frontier models are extraordinary and worth every cent —
  on the tasks that need them. The point is to *spend the premium where it buys
  something*, which requires knowing where it doesn't.
- **Not about squeezing pennies.** The savings from this discipline are real but
  that's a side effect. The deeper benefit is *intentionality*: you always know
  why you used the model you used.
- **Not a fixed config.** Your hardware, your task mix, and the model landscape
  all differ from anyone else's and all change over time. This is a way of
  *deciding*, not a setting to copy.

## Where to go next

- [Delegation map](./02-delegation-map.md) — turn this philosophy into a concrete
  task-class → model-class routing table.
- [Escalation rules](./03-escalation-rules.md) — the explicit list of reasons that
  justify paying.
