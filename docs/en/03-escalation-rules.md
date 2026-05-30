# 03 · Escalation rules: when paying is justified

[🇵🇱 Polski](../pl/03-escalation-rules.md) · [↑ README](../../README.md)

---

The delegation map says *where to start*. This document says *when to leave the
cheap default*. The goal is a short, explicit list of reasons — short enough that
"it might be better" can't sneak onto it.

## The four reasons (a decision frame)

Escalate to a paid model when **at least one** of these holds. If none holds, stay
local.

### 1. Capability gate — the local model literally can't

Some things free local models cannot do, full stop:

- **Live, online research** with current sources.
- **Context larger than your local model can hold** — a corpus that simply won't
  fit.

These aren't "escalations" in the discipline sense. They're a different tool for a
different job. Pay without hesitation; there's no cheaper path that works.

### 2. Stakes are high — irreversible or expensive to get wrong

When a decision is hard to undo or costly to repair, a second or third
*independent* paid opinion can be worth its price as insurance:

- Architectural decisions that touch many parts of a system.
- Irreversible operations (data migrations, anything against production).
- A contract or commitment you can't easily walk back.

The test isn't "is this important to me emotionally" — it's "what does it cost to
be wrong here?" If being wrong is cheap to fix, escalation is insurance you don't
need.

### 3. Deadlock — cheap options disagree or are both unsure

When two independent cheap perspectives genuinely conflict, or both express low
confidence, a third paid voice can break the tie. The key word is *genuinely*:
this is for real deadlock, not for "I'd feel better with one more check."

### 4. Critical deliverable — quality is the product

When the output *is* what a client pays for and quality is the differentiator —
an offer, a report, client-facing copy in a language where nuance matters — the
premium can be justified by the deliverable's value, not the task's difficulty.

## Example thresholds — **adjust to your context**

> ⚠️ The numbers below are **illustrative defaults to start a conversation with
> yourself**, not prescriptions and not anyone's "real" operating values. Your
> hardware, your rates, and your risk tolerance set your actual thresholds.
> Treat these as the *shape* of a threshold, then replace them.

- **Context size:** escalate to paid-long-context when input exceeds *roughly the
  comfortable working limit of your local-large model*. Where that line sits
  depends entirely on your machine — find yours, then make it the rule.
- **Stakes:** a rough starting heuristic is "if being wrong here would cost more
  than a few hours of rework, buy the second opinion." Set the bar where your own
  time and risk make sense.
- **Deadlock:** escalate after *two* independent cheap reviews conflict — not
  after one ambiguous answer.
- **Deliverable value:** escalate when the output's value to the client clearly
  exceeds the marginal API cost by a wide margin — the ratio matters, not the
  absolute price.

The point of writing thresholds down at all is to make escalation a *rule you can
check*, not a *mood you can rationalize*. Whatever numbers you choose, the
discipline is in having chosen them in advance.

## The five-second test (use it every time)

Before any escalation, ask:

> *"Is this genuinely hard or strategic — or is the paid model just more
> convenient right now?"*

If you can't name the specific thing the cheap model would get wrong, you've
failed the test. Stay local.

## A note on surprise bills

Escalation discipline has a second purpose beyond saving money: **avoiding
surprise**. Paid APIs can charge in ways that aren't obvious until the invoice —
background usage, retries, "thinking" tokens billed at output rates, a forgotten
loop. Two safeguards:

- **Know your provider's cost-surprises** before you rely on it. Some bill hidden
  work (internal reasoning, tool retries) at premium rates. Find out *which*
  before, not after.
- **Make every paid call a deliberate act.** The whole methodology pushes paid
  usage toward being intentional and rare — which is also the best defense against
  a bill you didn't see coming.

## Tell the user / tell yourself

A small habit that compounds: when you *do* escalate, **name the reason out loud**
(in a log, a comment, or just to yourself) — "using a paid model because this is
online research" or "because this decision is irreversible." Naming the reason
does two things: it confirms a real reason exists, and it builds a record you can
audit later. An escalation you can't narrate is one you probably shouldn't have
made.

## Where to go next

- [Cross-model review](./04-cross-model-review.md) — how the "second and third
  opinion" actually works, and where it fails.
- [Cost lessons](./05-cost-lessons.md) — what happens when this discipline slips.
