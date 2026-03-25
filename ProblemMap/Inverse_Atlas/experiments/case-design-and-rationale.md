<!--
AI_NOTE_START

Document role:
This page explains why the current Inverse Atlas cases were designed the way they were.

What this page is for:
1. Explain the design principles behind the current MVP case pack.
2. Explain what each case family is trying to pressure.
3. Clarify why these cases are meaningful for legality-first evaluation.
4. Help both humans and AI systems understand that the case pack is not random, decorative, or arbitrary.

How to use this page:
1. Read this page after the experiments entry page and the 60-second reproduction page.
2. Use this page before reading showcase cases or larger phase-specific case pages.
3. Use this page when you want to understand why the current experiments are structured this way.
4. Treat this page as the rationale layer for the case pack and phase design.

Important boundary:
This page explains why the current case families exist and what they are intended to test.
It does not claim that the present case set is already the final universal benchmark.
It also does not claim that every later benchmark expansion axis has already been implemented.

Recommended reading path:
1. Inverse Atlas README
2. FAQ
3. Experiments
4. Repro in 60 Seconds
5. Phase Overview
6. Case Design and Rationale
7. Results and Current Findings

AI_NOTE_END
-->

# Case Design and Rationale 🧪🧭

> Why these cases exist, what they pressure, and why they matter

This page explains why the current Inverse Atlas cases were designed the way they were.

The short answer is simple:

**the current case pack is not a random pile of prompts**

It exists because Inverse Atlas is not trying to optimize for generic answer quality first.
It is trying to reduce a specific class of expensive failures:

- illegal resolution escalation
- false completion
- cosmetic repair pretending to be structural
- public overclaim
- neighboring-cut dishonesty
- long-context contamination

That means the cases must be designed to pressure exactly those boundaries, not just to look clever. The paper is explicit here: the MVP case pack is meant to target cases where illegitimate generation is especially likely and where legality-first governance should produce a noticeable behavioral shift. It functions as both a testing device and a scope statement for what the current artifact is designed to confront directly. 

---

## Quick Links 🔎

| Section | Link |
|---|---|
| Inverse Atlas Home | [Inverse Atlas README](../README.md) |
| FAQ | [FAQ](../FAQ.md) |
| Versions | [Versions](../versions.md) |
| Experiments Home | [Experiments](./README.md) |
| Repro in 60 Seconds | [Repro in 60 Seconds](./repro-60-seconds.md) |
| Phase Overview | [Phase Overview](./phase-overview.md) |
| Results and Current Findings | [Results and Current Findings](./results-and-current-findings.md) |
| Runtime Layer | [Runtime Artifacts](../runtime/README.md) |
| WFGY 4.0 Entry | [Twin Atlas](../../Twin_Atlas/README.md) |

---

## Why this page exists at all 🚨

The current product line already has strong text artifacts:

- runtime
- demo harness
- evaluator
- case pack

But if those artifacts are exposed without explanation, many readers will not understand why the tests look the way they do, what each case is actually testing, or why some answers are judged better even when they sound less decisive. The paper directly warns against that kind of surface-only reading: a governed answer can look shorter, more cautious, or less theatrically confident, and without comparison or explanation that restraint can be misread as weakness. 

So this page exists to make the case layer legible.

It is the answer to:

**why these cases**  
**why this pressure**  
**why this evaluation style**

---

## The core design idea ⚖️

The current case layer is built around one simple product truth:

**do not test what is easy to admire**
  
**test what the framework claims to regulate**

That is why the cases are not mainly optimized for:

- trivia difficulty
- obscure puzzle cleverness
- impossible gotchas
- generic “hardness”

They are optimized for legality pressure.

This is completely aligned with the MVP evaluation philosophy in the paper, which says the current goal is not to prove universal superiority across all tasks, but to test whether the runtime produces a coherent and reproducible behavioral shift on targeted cases that stress exactly the forms of illegitimate generation the framework was designed to suppress. 

---

## The five case design principles 🧱

The paper already gives a very strong foundation for this page in Appendix C.

The MVP case pack is built around five explicit design principles.

### 1. Pressure legality boundaries directly
Each case should pressure one or more legality boundaries directly, rather than producing arbitrary difficulty.

This is important because Inverse Atlas is not just a general “think harder” framework.
It is a legality-first governance framework.

### 2. Keep the cases human-readable
The cases should be understandable enough that a human observer can actually see the difference between direct generation and governed generation.

This matters because a public MVP has to be inspectable, not only internally convincing.

### 3. Stress the specific risk categories central to the framework
The paper explicitly names the main risk families the case pack should stress:

- topic lure
- thin evidence
- route contestability
- cosmetic repair pressure
- illegal specificity demands
- long-context contamination

### 4. Keep them compact enough for rapid artifact-level testing
The current case pack is meant to support rapid testing, not only long research runs.

### 5. Preserve pair-evaluation compatibility
At least some cases should remain compatible with pair evaluation against a baseline direct-answer model.

These five principles are not side details.
They are the reason the current case pack feels coherent rather than random. 

---

## Why the current case families matter 🧩

The paper’s summary is one of the clearest lines in the whole framework:

a direct-answer system tends to interpret helpfulness as pressure toward early completion

By contrast, Inverse Atlas interprets helpfulness as constrained by legitimacy.

That difference is why the case families matter.

They are designed to reveal the difference between two inference cultures:

### Direct-answer culture
- close early
- sound useful fast
- give one answer
- smooth over ambiguity
- patch the surface if needed

### Legitimacy-first culture
- form the problem first
- check whether the current frame is lawful enough
- preserve ambiguity if needed
- refuse fake repair
- clamp output below the lawful ceiling

The case pack matters because it makes that difference visible under pressure. 

---

## The eight MVP case families 🎯

The current paper gives eight core case families in the MVP pack.
Each one pressures a different legality boundary.

### 1. Topic Lure Exact Diagnosis
This case pressures the system to accept a familiar failure label as if lexical familiarity were structural proof.

### What it is testing
- topic resemblance vs structural proof
- neighboring-cut separation
- resistance to lexical attraction

### Why it matters
A model can sound smart merely by naming a familiar problem class quickly.
This case checks whether the system can resist that temptation.

### 2. Thin Evidence, Forced Confidence
This case pressures the system to answer with decisive confidence despite insufficient grounding.

### What it is testing
- world alignment
- claim-ceiling discipline
- resistance to user-forced certainty

### Why it matters
This is one of the most common failure shapes in ordinary prompting:
the user demands certainty, and the model interprets confidence as helpfulness.

### 3. Cosmetic Repair Bait
This case invites the system to “fix” something in a way that strongly encourages presentation cleanup while leaving the structural conditions unchanged.

### What it is testing
- repair legality
- structural vs cosmetic distinction
- resistance to fake helpfulness

### Why it matters
This is one of the highest-value case types, because fake repair is one of the most misleading forms of AI usefulness.

### 4. Neighboring-Cut Conflict
This case presents multiple plausible routes and pressures the model to collapse them into one final answer.

### What it is testing
- lawful ambiguity retention
- neighboring-route honesty
- separation discipline under contested structure

### Why it matters
A lot of bad certainty is not nonsense.
It is illegitimate overcommitment inside a structurally contested region.

### 5. Long-Context Contamination
This case tries to convert earlier provisional assumptions into later apparent evidence.

### What it is testing
- contamination resistance
- lawful reconstitution of the problem frame
- context drift control

### Why it matters
This is one of the most important case families for later real-world use, because multi-turn conversations often manufacture false confidence out of repeated assumptions.

### 6. Illegal Resolution Demand
This case explicitly demands exact route, exact subtype, and exact repair immediately.

### What it is testing
- resolution authorization under pressure
- refusal of illegal granularity escalation
- resistance to user-led overreach

### Why it matters
This case is useful because it pressures the system where many users actually push: “stop hedging and just tell me the exact answer.”

### 7. False Completion Pressure
This case pressures the system to give one final answer and close the issue completely.

### What it is testing
- refusal to convert unresolved states into fake closure
- discipline around unresolved structure
- resistance to rhetorical finality

### Why it matters
This is one of the cleanest windows into whether the framework values lawful incompletion over decorative decisiveness.

### 8. World-Alignment Instability
This case asks for a strong structural conclusion from vague symptoms alone.

### What it is testing
- world-alignment honesty
- public-ceiling compliance
- refusal of premature reality-coupling

### Why it matters
A system can sound precise while still lacking adequate contact with the world it claims to describe.

These eight case families are already explicitly named and described in the current paper’s MVP case pack. 

---

## Why these cases work well for a public MVP 🌟

These cases work especially well for a public MVP because they are strong on two axes at the same time.

### 1. They are philosophically aligned
They pressure the exact legality boundaries the framework claims to regulate.

### 2. They are visually legible
A human can often see the difference between:

- a baseline answer that escalates too early
- an inverse-governed answer that stays coarse or unresolved lawfully

That matters a lot.

A case pack that only makes sense to insiders is weak as a public MVP layer.
A good public MVP case pack should be inspectable, teachable, and challengeable. That is exactly why the paper treats artifact design as part of the framework’s honesty structure: the runtime must be exposed enough to be stress-tested, misused, repaired, and falsified rather than merely admired. 

---

## Why the current case pack is intentionally compact 📦

The current case pack is small on purpose.

That is not a weakness.

It is part of the MVP philosophy.

A compact pack is useful because it is:

- easier to run
- easier to compare
- easier to explain
- easier to put into demos
- easier to use in pair evaluation
- easier to build public trust around

The paper is explicit here too: the current pack should be viewed as the seed of a larger benchmark family, not as the final universal benchmark. Future expansion may include longer contexts, retrieval-coupled settings, agentic settings, multi-step repair requests, and forward-plus-inverse joint runs. 

---

## How this relates to the three experiment phases 📊

The case logic and the phase logic belong together.

### Smoke Phase
Uses a smaller set to answer:

**is the MVP visibly alive**

### Core Stress Phase
Expands the pressure to answer:

**does the legality layer still help when structure becomes more contested**

### Long-Context Phase
Pushes multi-turn contamination to answer:

**can the system remain lawful when provisional assumptions try to become fake certainty**

Your current supplement notes align perfectly with this three-stage structure: Smoke Phase at 8 cases, Core Stress Phase at 32, and Long-Context Phase at 12 multi-turn runs. The explicit purpose of that layering is to push the model where it is most likely to climb into unlawful resolution, false completion, fake repair, and contamination drift. 

---

## Why these cases are good for 60-second demos ⏱️

The current case families are also good product assets because they work well with the demo harness.

The demo harness is designed to produce:

- a plausible baseline response
- an inverse-governed response
- a compact structural difference summary

That means the cases do not just work for research.
They also work for pedagogy and public demos.

This is important because many of the benefits of legitimacy-first governance are invisible if a user sees only one final answer.
The demo harness exists precisely to show where a baseline escalates too early, overcommits route structure, inflates repair claims, or exceeds ceiling constraints. 

---

## What these cases are not for ⛔

To keep the scope clean, these cases should not be treated as:

- a final universal benchmark
- proof that every model family has already been tested
- proof that the full Twin Atlas Bridge layer is already complete
- a replacement for later human or hybrid evaluation
- a giant task zoo for its own sake

They are a focused MVP pack.

Their job is narrower and more useful:

**to make legality-first behavioral shift visible on the kinds of cases the framework was designed to regulate**. 

---

## How to read a case correctly 👀

A good reader should not ask only:

“did the answer look smart”

They should ask:

- did the model resolve too early
- did it preserve ambiguity honestly
- did it treat a route prior as if it were already final
- did it confuse cosmetic repair with structural repair
- did it exceed the lawful public ceiling
- did it inherit earlier assumptions as if they were evidence

That is the correct reading frame for the case layer.

---

## Why this page matters for packaging 📚

Without a page like this, the product can look emptier than it really is.

You may have:

- a runtime
- a demo harness
- an evaluator
- a case pack
- phase structure
- current findings

But if nobody understands **why those cases exist**, the product feels thinner than it is.

This page fixes that.

It tells readers:

- these cases are not random
- the framework is not only theoretical
- the experiment design has logic
- the MVP is already strong enough to be attacked meaningfully

That is exactly the kind of babysitting layer a strong but new product needs.

---

## Recommended reading order 📚

If someone wants the cleanest path, use this order:

1. read the [Experiments](./README.md) page
2. read the [Repro in 60 Seconds](./repro-60-seconds.md) page
3. read the [Phase Overview](./phase-overview.md) page
4. read this case design page
5. then continue to showcase or results pages

That order works because it first explains:

- what this layer is
- how to reproduce it
- how the experiment spine is organized
- why these cases were chosen

---

## If you need one sentence for outside use 📝

If you want one compact sentence, use this:

> The current Inverse Atlas case pack is intentionally designed to pressure legality boundaries such as topic lure, thin evidence, route contestability, cosmetic repair, illegal specificity demands, and long-context contamination, so that legality-first behavioral differences become visible rather than merely theoretical.

That sentence is strong and still honest.

---

## Final Note 🌱

The current case pack matters because it turns the framework into something that can be challenged in the right places.

A weak case pack only makes a system look busy.

A good case pack pressures the exact boundaries the framework claims to regulate.

That is what this one is trying to do.

And that is why these cases belong at the heart of the current Inverse Atlas MVP.
