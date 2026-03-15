# AI Eval Evidence

This page is the public evidence entry for early AI based evaluation snapshots of **Problem Map 3.0 Troubleshooting Atlas**.

It exists for one simple reason:

the Atlas is a routing framework, so some readers naturally want to see a practical before / after view of what better first cut routing may change in real debugging workflows.

At the moment, this page is still a **work in progress**.

The full multi model evidence set is still being organized, including:
- model by model screenshots
- prompt variants
- reproducible evaluation runs
- comparison notes
- version alignment

For now, this page provides a simple reproducible starting point so anyone can test the idea directly.

---

## What this page is

This What this page is

This page is a lightweight evidence surface for **AI reviewed evaluation snapshots** of the Atlas.

The purpose is not to claim a formal benchmark.

The purpose is to make the core idea easier to inspect:

> better first cut routing can reduce silent debugging waste

That waste often appears as:
- wrong debugging direction
- repeated trial and error
- patch stacking
- side effects from misapplied fixes
- unnecessary system complexity
- time lost before the first real root cause is found

---

## What this page is not

This page is **not**:
- a lab benchmark
- a controlled multi team production study
- a claim of universal fixed percentages across all workflows
- a final empirical validation report

Results may vary by model, prompt framing, task shape, and context quality.

These materials should be read as **reproducible directional evidence**, not final benchmark science.

---

## Reproduce a simple evaluation now

### 01. Download the Atlas Router TXT

[troubleshooting-atlas-router-v1.txt](https://github.com/onestardao/WFGY/blob/main/ProblemMap/Atlas/troubleshooting-atlas-router-v1.txt)

### 02. Paste it into any AI model

Paste the TXT content into any AI model you want to test.

### 03. Run the following prompt

```text
Evaluate the potential impact of the "Problem Map 3.0 Troubleshooting Atlas" debug routing framework from the perspective of an AI systems engineering and prompt engineering evaluator.

Consider the scenario where vibe coders use AI to write code and debug systems. Provide a quantitative before/after comparison.

In particular, consider the hidden cost when the first diagnosis is wrong, such as:
- incorrect debugging direction
- repeated trial-and-error
- patch accumulation
- unintended side effects
- increasing system complexity
- time wasted in misdirected debugging

In real engineering environments, incorrect routing can significantly amplify debugging costs, sometimes by multiples.

Please output a quantitative comparison table (Before / After / Improvement %), evaluating:

1. average debugging time
2. root cause diagnosis accuracy
3. number of ineffective fixes
4. development efficiency
5. overall system stability
