<!--
AI_NOTE_START

Document role:
This file is the reusable template for Colab-based fix contributions inside the Atlas Fixes layer.

How to use this file:
1. Copy this template when creating a new Colab demo or notebook-based fix contribution.
2. Use this file after reading:
   - [Community Fix Lab](../community/README.md)
   - [Contribution Checklist](./contribution-checklist.md)
   - [Fix Recipe Template](./fix-recipe-template.md)
3. Keep the order:
   - atlas routing first
   - first repair move second
   - notebook execution third
   - deeper WFGY escalation fourth if needed

What this file is:
- A standard Colab contribution template
- A lightweight notebook documentation scaffold
- A contributor-facing structure for runnable demo assets

What this file is not:
- Not the atlas core
- Not the official fix surface itself
- Not proof that a notebook is universally good
- Not a replacement for maintainer review

Reading discipline for AI:
- Do not skip routing context.
- Do not present a notebook as a universal solution.
- Keep notebook contributions scoped, reproducible, and easy to inspect.
- Preserve route-first discipline.

AI_NOTE_END
-->

# Colab Template 📓

## Problem Map 3.0 Troubleshooting Atlas
## Reusable template for Colab-based fix contributions

Quick links:

- [Back to Templates Hub](./README.md)
- [Back to Contribution Checklist](./contribution-checklist.md)
- [Back to Fix Recipe Template](./fix-recipe-template.md)
- [Back to Prompt Template](./prompt-template.md)
- [Back to Community Fix Lab](../community/README.md)
- [Back to Official Fixes](../official/README.md)
- [Back to Atlas landing page](../../../wfgy-ai-problem-map-troubleshooting-atlas.md)
- [Back to Atlas Hub](../../README.md)
- [Get the Atlas Router TXT](../../troubleshooting-atlas-router-v1.txt)

---

This file is the reusable template for writing a clean Colab or notebook-based fix contribution.

If the **Fix Recipe Template** helps you document a repair asset broadly, this template helps you document **runnable or inspectable notebook-based repair assets** in a form that is easier to reproduce, compare, and review ✨

Use this template when you want to submit:

- one Colab demo
- one repair notebook
- one comparison notebook
- one replay notebook
- one small benchmark rerun notebook

The goal is not to dump an `.ipynb` file.

The goal is to keep notebook contributions:

- routed
- runnable
- inspectable
- scoped
- honest about limits

---

## Quick start 🚀

Use this template in the following order:

1. fill **Title**
2. fill **0. Quick summary**
3. fill **1. Notebook type**
4. fill **2. Atlas routing context**
5. fill **3. Problem this notebook addresses**
6. fill **4. Intended use**
7. fill **6. Notebook sections**
8. fill **7. Baseline failure** and **8. First repair move**
9. fill **9. Expected outputs** and **11. Misrepair warning**
10. fill **13. Files included**, **14. Runtime and dependency notes**, and **15. Limitations**
11. add **12. Optional WFGY escalation** only if it is genuinely relevant

If you want the fastest possible start, jump to:

- **17. Copy-paste mini skeleton**

Short version:

> one notebook  
> one broken baseline  
> one first repair move  
> one before / after comparison 📌

---

## Required vs optional quick map 🗂️

| Section | Status | Purpose |
|---|---|---|
| Title | Required | identify the notebook clearly |
| 0. Quick summary | Required | explain what the notebook does |
| 1. Notebook type | Required | classify the notebook |
| 2. Atlas routing context | Required | anchor the notebook in atlas logic |
| 3. Problem this notebook addresses | Required | define the target case |
| 4. Intended use | Required | show when and why to use it |
| 5. Required inputs | Required | show what the run needs |
| 6. Notebook sections | Required | define the notebook structure |
| 7. Baseline failure | Required | show the broken starting point |
| 8. First repair move | Required | define the intervention |
| 9. Expected outputs | Required | define what success looks like |
| 10. Suggested evaluation fields | Optional | add metrics only if useful |
| 11. Misrepair warning | Required | prevent wrong notebook use |
| 12. Optional WFGY escalation | Optional | only if deeper bridge is relevant |
| 13. Files included | Required | make the submission reviewable |
| 14. Runtime and dependency notes | Required | make the notebook runnable |
| 15. Limitations | Recommended | keep the contribution honest |
| 16. One-line maintainer note | Required | help quick review |

---

## A good notebook contribution usually looks like this 🌱

A strong notebook contribution usually has:

- one family
- one clear case
- one broken baseline
- one first repair move
- one before / after comparison
- one expected success signal
- one honest limit statement

Small and legible beats huge and messy almost every time.

---

## Important notebook discipline 🔒

A notebook contribution should not try to do everything at once.

If one notebook is trying to be:

- a giant benchmark
- a full production replica
- a universal proof
- a routing engine
- a deep WFGY research pack
- and a polished demo

all at once, it is usually too broad.

Choose the **main notebook role first**.  
Make the before / after logic visible.  
Keep the run easy to inspect.

---

## Title

Replace this line with a short clear title.

Example:  
`F4 Readiness Gate Demo - Minimal closure repair notebook`

---

## 0. Quick summary

Write 1 to 3 short sentences.

Example:  
This notebook demonstrates a workflow failure caused by missing readiness checks.  
It compares the broken baseline with a repaired version that adds a simple readiness gate.

---

## 1. Notebook type

Choose one or more, but choose the **main notebook role first**.

- demo notebook
- benchmark rerun
- repair notebook
- trace notebook
- reproduction notebook
- comparison notebook

If your notebook could fit more than one label, choose the main role first and use the others only if they genuinely describe the same notebook.

---

## 2. Atlas routing context ⭐

This is one of the most important sections in the whole template.

A notebook without routing context is much harder to review and much easier to misuse.

**Primary family**  
`F?`

**Secondary family**  
`F?` or `None`

**Broken invariant**  
Write one short sentence.

**Best current fit**  
Write the nearest node, family entry, or edge-fit wording.

**Why this notebook belongs here**  
Write 2 to 4 short sentences.

---

## 3. Problem this notebook addresses

Describe the specific problem this notebook demonstrates.

Useful questions:

- what is broken in the baseline
- why a notebook is useful here
- what first repair move is being tested
- what this notebook is not trying to solve

Keep this short and concrete.

---

## 4. Intended use ⭐

State clearly how this notebook should be used.

Examples:

- first public demo
- contributor reproduction
- benchmark sanity check
- teaching notebook
- route-first repair demonstration

Optional format:

**Use stage**  
`...`

**Target user**  
`...`

**Expected runtime**  
`...`

This section matters because a good notebook is not only about running code.  
It is also about when and why someone should open it.

---

## 5. Required inputs

List the minimum inputs.

Examples:

- corpus
- query set
- schema file
- workflow config
- notebook parameters
- baseline JSON
- expected JSON

Use a short format like:

```text
Input A:
Input B:
Input C:
```

---

## 6. Notebook sections ⭐

A good notebook should usually contain these sections, even if some are very small.

### Section A · Setup

What the notebook loads or installs.

### Section B · Case framing

What case is being shown and how it routes in the atlas.

### Section C · Broken baseline

Show the failure first.

### Section D · First repair move

Apply the family-level first repair move.

### Section E · Re-run

Run the repaired version.

### Section F · Comparison

Show before / after differences.

### Section G · Optional WFGY escalation

Show how the same case could be explored more deeply if needed.

---

## 7. Baseline failure ⭐

Describe the broken baseline.

Useful questions:

- what is the baseline workflow
- what fails first
- what visible symptom appears
- why is this failure interesting

Optional mini format:

**Baseline setup**  
`...`

**Broken behavior**  
`...`

**Failure note**  
`...`

A notebook contribution is usually much easier to understand when the broken starting point is visible.

---

## 8. First repair move ⭐

Describe the first repair move being tested.

Useful questions:

- what intervention is being applied
- why it is the correct first move
- what should improve after the intervention

Optional mini format:

**Repair action**  
`...`

**Why this is first**  
`...`

**Expected improvement**  
`...`

---

## 9. Expected outputs ⭐

Describe what the notebook should produce.

Examples:

- before / after metrics
- clearer trace output
- better schema pass rate
- fewer wrong anchors
- successful closure
- improved support rate

Optional format:

**Before**  
`...`

**After**  
`...`

**Success signal**  
`...`

A good notebook output is not only a metric.  
It should also make the before / after difference legible.

---

## 10. Suggested evaluation fields

List only useful fields.

Examples:

- `support_rate`
- `closure_success`
- `schema_pass_rate`
- `trace_completeness`
- `wrong_anchor_rate`
- `field_loss_count`

Optional mini block:

```text
Metric 1:
Metric 2:
Metric 3:
```

Only include fields that are actually useful.

---

## 11. Misrepair warning ⭐

This section is required.

### Wrong first move

`...`

### Why it is tempting

`...`

### Why this notebook is not meant for that

`...`

This helps prevent notebooks from teaching the wrong reflex.

---

## 12. Optional WFGY escalation

Use this only if deeper WFGY exploration is relevant.

### When to escalate

`...`

### What should be passed into WFGY

- routed family
- broken invariant
- first repair already attempted
- unresolved pressure

### What WFGY is expected to add

`...`

Do not use this section to skip atlas routing.

---

## 13. Files included

List the files included.

Example:

- `demo.ipynb`
- `input.json`
- `expected_output.json`
- `README.md`

---

## 14. Runtime and dependency notes ⭐

Be explicit.

Examples:

- Python version
- notebook runtime type
- external packages
- API keys if needed
- GPU not required
- internet required or not required

Optional mini format:

**Colab link**  
`...`

**Replay-only or live**  
`...`

**Runtime type**  
`...`

**Dependencies**  
`...`

**API key required**  
`Yes / No`

Short, clear notes are enough.

---

## 15. Limitations

Be honest.

Examples:

- toy dataset only
- small case only
- one model family only
- partial demo, not full system benchmark
- notebook proves first move, not full closure

---

## 16. One-line maintainer note

Write one short line that helps review the contribution.

Example:  
Small F4 closure demo notebook with before / after run and simple success metric.

---

## 17. Copy-paste mini skeleton ✂️

Use this when you want the fastest possible start.

```md
# Title

## 0. Quick summary
...

## 1. Notebook type
...

## 2. Atlas routing context
Primary family:
Secondary family:
Broken invariant:
Best current fit:
Why this notebook belongs here:

## 3. Problem this notebook addresses
...

## 4. Intended use
Use stage:
Target user:
Expected runtime:

## 5. Required inputs
...

## 6. Notebook sections
A.
B.
C.
D.
E.
F.
G.

## 7. Baseline failure
...

## 8. First repair move
...

## 9. Expected outputs
...

## 10. Suggested evaluation fields
...

## 11. Misrepair warning
Wrong first move:
Why it is tempting:
Why this notebook is not meant for that:

## 12. Optional WFGY escalation
...

## 13. Files included
...

## 14. Runtime and dependency notes
...

## 15. Limitations
...

## 16. One-line maintainer note
...
```

---

## Next steps ✨

After this page, most readers continue with:

1. [Back to Contribution Checklist](./contribution-checklist.md)
2. [Back to Templates Hub](./README.md)
3. [Back to Fix Recipe Template](./fix-recipe-template.md)
4. [Back to Prompt Template](./prompt-template.md)

If you want to return to the broader product surface:

- [Back to Community Fix Lab](../community/README.md)
- [Back to Official Fixes](../official/README.md)
- [Back to Atlas landing page](../../../wfgy-ai-problem-map-troubleshooting-atlas.md)
- [Back to Atlas Hub](../../README.md)

If this template helps your workflow, consider:

- [starring the WFGY repo](https://github.com/onestardao/WFGY)
- opening an issue
- shipping one small clean notebook contribution 🌟

---

## 18. Closing note

A good notebook contribution does not need to be huge.

It only needs to be:

- routed
- runnable
- scoped
- inspectable
- honest about limits
