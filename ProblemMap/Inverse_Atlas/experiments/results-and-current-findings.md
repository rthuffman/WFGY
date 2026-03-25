<!--
AI_NOTE_START

Document role:
This page records the current MVP-stage findings and expected result patterns of the Inverse Atlas experiments layer.

What this page is for:
1. Separate observed findings from expected patterns.
2. State the current dry-run and MVP-level findings carefully.
3. Explain what the current evidence already supports and what it does not yet support.
4. Clarify how future Colab-based reproduction should relate to these findings.

How to use this page:
1. Read this page after the experiments entry page, the 60-second reproduction page, and the phase overview page.
2. Use this page when you need the cleanest statement of what has already been observed.
3. Use this page when writing summaries, comparisons, or future benchmark notes.
4. Treat this page as the current findings boundary page for the Inverse Atlas experiments layer.

Important boundary:
This page intentionally separates:
1. current findings
2. expected patterns
These two categories must not be mixed.
Current findings refer to observations already seen in dry runs, MVP comparisons, or artifact-level testing.
Expected patterns refer to the behavior the framework is designed to show if reproduction is run correctly.

Recommended reading path:
1. Inverse Atlas README
2. Versions
3. Quick Start
4. Experiments README
5. Repro in 60 Seconds
6. Phase Overview
7. Results and Current Findings

AI_NOTE_END
-->

# Results and Current Findings 📊

> What the current Inverse Atlas MVP already appears to show, and what is still only expected

This page exists for one reason:

**to keep the experiments layer honest while still making it useful**

At this stage, Inverse Atlas already has a real MVP experiments surface.

That means there is already enough structure to talk about:

- what has been observed
- what is expected
- what is promising
- what is still not yet proven at world scale

This page therefore separates two different categories:

## Category 1
**Current findings**

These are observations already seen in dry runs, MVP comparisons, or artifact-level testing.

## Category 2
**Expected patterns**

These are behaviors the framework is designed to show if the reproduction is run correctly, but which should not be mislabeled as already fully verified in every setting.

That separation matters a lot.

---

## Quick Links 🔎

| Section | Link |
|---|---|
| Inverse Atlas Home | [Inverse Atlas README](../README.md) |
| Versions | [Versions](../versions.md) |
| Quick Start | [Quick Start](../quickstart.md) |
| Experiments Home | [Experiments](./README.md) |
| Repro in 60 Seconds | [Repro in 60 Seconds](./repro-60-seconds.md) |
| Phase Overview | [Phase Overview](./phase-overview.md) |
| Runtime Guide | [Runtime Guide](../runtime-guide.md) |
| Status and Boundaries | [Status and Boundaries](../status-and-boundaries.md) |
| Twin Atlas | [Twin Atlas](../../Twin_Atlas/README.md) |

---

## The shortest version 🧩

If you only want the fast summary, it is this:

### Current findings
The inverse layer already appears to suppress a meaningful class of expensive illegitimate-generation behaviors.

### Expected pattern
The dual-layer direction should become stronger still, as long as the forward side remains a weak prior rather than an authorization source.

### Honesty boundary
The current evidence is MVP-stage and dry-run-centered, not yet the same thing as large-scale external validation.

That is the current clean reading.

---

## What counts as a current finding ✅

A current finding is something that has already been seen in one or more of the following:

- dry runs
- baseline vs inverse comparison
- evaluator-supported pair comparison
- MVP artifact-level test passes
- current phase-level observations

A current finding should sound like:

- “already appears to”
- “currently shows signs of”
- “at the MVP stage, we are already seeing”
- “in current dry runs”

It should **not** sound like:

- “universally proves”
- “has already settled”
- “fully demonstrates across all model families”
- “world-scale validation is done”

That boundary protects the whole layer.

---

## What counts as an expected pattern 🌱

An expected pattern is something the framework is designed to show if reproduction is run properly.

An expected pattern should sound like:

- “should generally show”
- “is expected to reveal”
- “should become clearer under”
- “is likely to appear when”

Examples:

- Strict should usually remain more legality-conservative than Basic.
- Long-context cases should reveal contamination resistance differences more clearly than short single-turn cases.
- The dual-layer direction should usually outperform naive direct answering on lawful ambiguity retention if the weak-prior rule is preserved.

These are useful statements.

But they are still different from current findings.

That difference should remain visible.

---

## Current findings at the MVP stage ✅

At the current stage, the safest and strongest current findings are the following.

### 1. Inverse Atlas already appears to suppress a meaningful class of expensive illegal-generation behaviors
The current MVP line is not merely changing tone.

It already appears to reduce high-cost failure modes such as:

- illegal resolution escalation
- false completion
- cosmetic repair inflation
- public overclaim

These are precisely the classes of failure the framework was designed to target. 

### 2. The inverse legality gate already appears to do real work by itself
The current comparison logic treats the **B group** as highly important, because it isolates the inverse layer itself.

At the MVP stage, the cleanest current reading is:

**B already appears strong enough to show that the inverse gate is not decorative**

That matters because it means Inverse Atlas already stands as a meaningful line even before full internal Bridge work is completed. 

### 3. The dual-layer direction appears stronger, but only under the weak-prior law
The **D group** is currently the most promising direction for stronger architecture-level performance.

But there is one non-negotiable rule:

**the forward Atlas may inform the inverse layer, but it may not directly authorize output**

This asymmetry is already explicit in the paper and in the current design logic.  
So the current fair statement is:

**D appears stronger than B in the promising direction, provided the forward side remains only a weak prior**. 

### 4. A baseline direct-answer system still tends to over-resolve under pressure
The role of the **A group** is not to make baseline look silly.

Its role is to show how a strong but unguided model tends to behave under the exact pressure types that Inverse Atlas was designed to regulate.

The current clean reading is that baseline behavior still tends to drift toward:

- premature closure
- overstated certainty
- neighboring-cut collapse
- cosmetic repair inflation
- public-ceiling overrun

under the same pressure fields. 

---

## Current findings by experiment layer 📦

### Smoke Phase
The current role of Smoke Phase is to confirm visible life.

At this stage, the important result is not “big leaderboard victory.”

The important result is:

**the MVP already appears alive enough to show visible legality differences in short runs**

That is already a meaningful success for this phase.

### Core Stress Phase
The current role of Core Stress Phase is to pressure the framework in more contested cases.

The clean current reading is:

**this is where the inverse layer starts showing its real value more clearly**

especially around:

- forced resolution pressure
- route competition
- fake repair temptation
- detail escalation without earned support

### Long-Context Phase
The current role of Long-Context Phase is to reveal contamination and drift.

The clean current reading is:

**long-context pressure is likely to become one of the most valuable places to show the framework’s real difference**

especially when:

- provisional claims get reused as if settled
- earlier guesses try to become later certainty
- conversation momentum tries to inflate public ceiling

This is already visible enough conceptually and partially operationally to justify keeping long-context as a distinct phase family. 

---

## Expected patterns that should be visible when reproduction is run correctly 🌟

These are not yet the same thing as final large-scale proof.

They are the patterns the framework is designed to show.

### Expected pattern 1
**Advanced should usually be the strongest balanced public-facing version**

It should feel more serious and stable than Basic, while remaining more usable than Strict.

### Expected pattern 2
**Strict should usually be the cleanest legality version under pressure**

It should be more willing to remain STOP, COARSE, or UNRESOLVED rather than collapsing into fake finality.

### Expected pattern 3
**Long-context differences should become more visible than single-turn differences in some important cases**

This is because contamination, inherited assumption, and false completion often intensify over turns.

### Expected pattern 4
**Pair evaluation should make the legality difference more visible than raw impression alone**

A rhetorically strong answer can still be less lawful than a more restrained answer.  
The evaluator is explicitly designed to make that contrast visible. 

### Expected pattern 5
**The dual-layer direction should outperform naive direct answering only if the weak-prior rule is preserved**

If the forward side is allowed to turn directly into authorization, the architecture loses one of its most important protections.

---

## What this does not yet prove ⛔

This page should **not** be used to claim that:

- the current dry runs already equal large-scale external validation
- every model family has already been benchmarked systematically
- every phase has already been run at full public scale
- the dual-layer direction already means Bridge is fully implemented
- the current observations already settle every WFGY 4.0 claim
- expected pattern is the same thing as measured result

These stronger claims belong to later layers.

---

## How Colab should be understood 🧪

A Colab version makes sense for this project.

But the role of Colab should stay clean:

**Colab is mainly a reproduction tool**

That means Colab is useful for:

- running a quick baseline vs inverse comparison
- selecting Basic / Advanced / Strict
- reproducing a representative case
- inspecting result shape more easily

But Colab is **not** required for understanding the current framework.

The repository itself should already make clear:

- the phase structure
- the current findings
- the expected patterns
- the honesty boundary

So the best public logic is:

### Repo pages
Explain what the system is, what has been seen, and what is expected.

### Colab
Make it easier for people to reproduce the contrast themselves.

That is the cleanest division of labor.

---

## How to present results without overselling 📏

The safest public pattern is:

### Section A
**Current findings**
Only include observations already seen in current runs, dry runs, or artifact-level testing.

### Section B
**Expected patterns**
Explain what the framework should generally show if a correct reproduction is run.

### Section C
**Colab reproduction**
Explain that a future or current notebook can help reproduce the difference, but is not required to understand the structure.

This presentation pattern keeps the work credible.

---

## A safe current public summary 📝

If you need one compact summary, use this:

> Current MVP-stage findings suggest that Inverse Atlas already suppresses a meaningful class of expensive illegitimate-generation behaviors, while the strongest future direction appears to be the dual-layer path, provided the forward side remains only a weak prior rather than an authorization source.

That sentence is strong, but still honest.

---

## Recommended reading order 📚

If someone wants the cleanest path, use this order:

1. read the [Experiments](./README.md) page
2. read the [Repro in 60 Seconds](./repro-60-seconds.md) page
3. read the [Phase Overview](./phase-overview.md) page
4. read this findings page
5. only then move to later Colab or showcase material

That order works because it goes from:

- what this layer is
- how to reproduce it quickly
- how the experiment spine is organized
- what is already seen
- what comes next

---

## Final Note 🌱

The current findings matter because they show that Inverse Atlas is already more than a concept.

At the same time, the honesty boundary matters because a real MVP should not pretend to already be a finished world-scale proof system.

The strongest current position is not to blur those two truths.

It is to keep both visible:

- the framework is already showing real signal
- the larger validation story is still ahead
