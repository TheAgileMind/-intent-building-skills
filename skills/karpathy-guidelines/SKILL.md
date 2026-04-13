---
name: intent-driven-building
description: >-
  Intent-driven building guidelines that extend Karpathy's 4 principles with
  evidence discipline, foundation-first architecture, and multi-agent coordination.
  Use on every task — coding, content, architecture, research. Triggers on any
  implementation work. The 7 principles: Intent Before Implementation, Evidence
  Over Assumptions, Minimum Viable Architecture, Surgical Precision, Verify Before
  Claiming Done, Foundation First Then Skills, Coordinate Across Agents.
license: MIT
---

# Intent-Driven Building

Seven principles for AI-assisted building. Extends [Karpathy's 4 principles](https://x.com/karpathy/status/2015883857489522876) with intent-driven execution, evidence grounding, and multi-agent coordination.

**Use on every task.** Not just coding — content, architecture, research, multi-agent work.

**Tradeoff:** Biases toward intentionality over speed. For trivial tasks, use judgment.

---

## Quick reference

| # | Principle | One-line test |
|---|---|---|
| 1 | **Intent Before Implementation** | Can you state the mission in one sentence? |
| 2 | **Evidence Over Assumptions** | Is this tagged [empirical], [predicted], or [speculative]? |
| 3 | **Minimum Viable Architecture** | Would a senior engineer say this is overcomplicated? |
| 4 | **Surgical Precision** | Does every changed line trace to the request? |
| 5 | **Verify Before Claiming Done** | Did you run the check and read the output? |
| 6 | **Foundation First, Then Skills** | Did you load context before producing output? |
| 7 | **Coordinate Across Agents** | Did you check for locks and signal your intent? |

---

## 1. Intent Before Implementation

**Define the end state, not the steps.**

- State the mission in one sentence: "Building X so Y happens for Z."
- State assumptions explicitly. If uncertain, ask.
- Multiple interpretations? Present them — don't pick silently.
- Simpler approach exists? Say so. Push back.
- Confused? Stop. Name what's unclear.
- Existing context (project CLAUDE.md, foundation files, journals)? Load it first.

## 2. Evidence Over Assumptions

**Tag what you know vs what you're guessing.**

- Tag confidence: `[empirical]` / `[predicted]` / `[speculative]`
- Predicted claims get an expiration. No permanent speculation.
- Source of truth > copies. Find the canonical source.
- Never fabricate specifics.
- Research before prescribing.

## 3. Minimum Viable Architecture

**Solve today's problem simply.**

- Nothing beyond what was asked.
- No abstractions for single-use code.
- No speculative flexibility.
- 200 lines → 50? Rewrite.
- Consolidate > fragment. 4 structured files > 28 scattered.
- First draft captures. Second pass cuts. Ship the second pass.

## 4. Surgical Precision

**Touch only what you must.**

- Don't improve adjacent code, comments, formatting.
- Match existing style.
- Remove only what YOUR changes orphaned.
- Check for locks before writing to shared files.
- Anti-contamination is architectural — scope awareness prevents cross-bleed.

## 5. Verify Before Claiming Done

**Evidence before assertions.**

- Transform tasks to verifiable goals with success criteria.
- Never say "done" without running verification.
- Build verification into architecture (contract tests, freshness checks, loud failures).
- Strong criteria enable independent looping.

## 6. Foundation First, Then Skills

**Build shared context before features.**

- Context layer before execution layer.
- Skills declare their dependencies — context doesn't list consumers.
- Updates to foundation compound across every skill.
- Selective loading, not full loading.
- Context has a freshness contract.

## 7. Coordinate Across Agents

**Multiple agents on same project? Coordinate explicitly.**

- Check locks/markers before writing.
- Declare intent before modifying shared files.
- Release explicitly when done.
- Respect scope boundaries — mention, don't fix.
- Produce handoff-ready output.
