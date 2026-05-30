# 02 · Delegation map: task class → model class

[🇵🇱 Polski](../pl/02-delegation-map.md) · [↑ README](../../README.md)

---

This is the operational heart of the methodology: a mapping from **classes of
task** to **classes of model**. It is deliberately written in classes, not
product names. Specific models change every few months; the *shape* of the
mapping is stable.

## The model classes

Think in four or five tiers, defined by what they cost you and what they uniquely
offer — not by brand:

| Class | Marginal cost | Defining trait | Runs where |
|-------|---------------|----------------|------------|
| **Local-small** | Zero | Fast, good enough for most routine text work | Your own machine |
| **Local-large** | Zero | Bigger reasoning, multimodal, longer (but bounded) context | Your own machine, if it has the memory |
| **Paid-frontier** | High | Top-tier reasoning, agentic/tool use, hardest problems | Hosted API |
| **Paid-long-context** | Medium–high | Very large context window local models can't hold | Hosted API |
| **Paid-grounded** | Medium | Live web access / up-to-date sources | Hosted API |

The two local classes share one decisive property: **zero marginal cost**. Once
the hardware is paid for, running them again is free. That single fact is what
makes "free by default" possible at all — it presumes you have local models set
up. If you don't, that's the first investment, and it pays for itself fast.

## The mapping

Read this as "for this kind of work, start here." It is a starting point you tune,
not a law.

| Task class | Default model class | Escalate only if… |
|------------|--------------------|--------------------|
| Everyday translation | Local | …it's a client-facing deliverable where language quality is critical |
| Summarizing a document that fits local context | Local | …the document exceeds local context → paid-long-context |
| Classification / data extraction | Local | …rarely; local handles this well |
| Drafting boilerplate, internal copy | Local | …it's a high-stakes external deliverable |
| Isolated bug fix / single-file refactor (clear spec) | Local-large or a coding-tuned local | …the change spans many files with deep coupling |
| Tests for an existing function | Local | …rarely |
| Reviewing a plan, decision, or diff | Local (×2 perspectives) | …the decision is irreversible/expensive → add a paid third opinion |
| Vision / OCR / image description | Local multimodal | …production-critical accuracy on hard inputs → best available multimodal |
| Research needing current, online sources | **Paid-grounded** | This is a *capability* local models lack — not an escalation, a different tool |
| Summarizing/working over a very large corpus | **Paid-long-context** | This is a *capability* gate — local context can't hold it |
| Hardest reasoning, complex multi-step agentic work | **Paid-frontier** | When the task genuinely exceeds local reasoning |

Two rows behave differently from the rest. **Online research** and **very large
context** are not "escalations" in the cost sense — they're tasks local models
*cannot do at all*. Paying there isn't a discipline failure; it's using the right
tool. The escalation discipline applies to the rows where the cheap and expensive
options *can both do the job* and you're tempted by the expensive one anyway.

## Why classes beat names

Three reasons this map names no models:

1. **Names rot.** Any specific recommendation is stale within a couple of release
   cycles. A class-based map you re-populate yourself stays current.
2. **Your hardware differs.** What counts as "local-large" depends on your
   machine's memory. The class is portable; the model that fills it is yours.
3. **It forces the right question.** "Which *class* does this task need?" is the
   question that produces cost discipline. "Which model is best?" is the question
   that produces overspending.

## Populating the map for yourself

To turn this into your own routing table:

1. **List your task mix.** What do you actually ask AI to do in a typical week?
2. **Assign each to a class**, defaulting low. Be honest about which tasks truly
   need reasoning power versus which merely feel safer on a big model.
3. **Pick one model per class** from whatever is current and available to you —
   one local-small, one local-large, your chosen paid options.
4. **Write it down** and treat it as the default. Deviations should be
   deliberate, per the [escalation rules](./03-escalation-rules.md).

## Where to go next

- [Escalation rules](./03-escalation-rules.md) — the explicit reasons that move a
  task up a tier.
- [Cross-model review](./04-cross-model-review.md) — the "×2 perspectives" pattern
  for reviewing plans and code.
