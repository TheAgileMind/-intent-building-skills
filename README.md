# Intent-Driven Building — Claude Code Guidelines

Seven principles for AI-assisted building. Fork of [forrestchang/andrej-karpathy-skills](https://github.com/forrestchang/andrej-karpathy-skills), extending Karpathy's 4 principles with intent-driven execution, evidence discipline, foundation-first architecture, and multi-agent coordination.

## The Problems (Karpathy's original observations)

> "The models make wrong assumptions on your behalf and just run along with them without checking."

> "They really like to overcomplicate code and APIs, bloat abstractions, don't clean up dead code... implement a bloated construction over 1000 lines when 100 would do."

> "They still sometimes change/remove comments and code they don't sufficiently understand as side effects, even if orthogonal to the task."

## What This Fork Adds

Karpathy identified that LLMs make wrong assumptions, overcomplicate code, and touch things they shouldn't. This fork extends those 4 principles into 7 by adding three layers from real multi-agent AI building experience:

| Karpathy's principle | This fork's extension | What's added |
|---|---|---|
| Think Before Coding | **Intent Before Implementation** | Commander's Intent — define the end state, not the steps. Load existing context before proposing. |
| Simplicity First | **Minimum Viable Architecture** | Consolidate > fragment. 4 structured files > 28 scattered. Tightening pass is part of the build. |
| Surgical Changes | **Surgical Precision + Coordination** | Lock protocols, anti-contamination rules, scope-aware multi-agent editing. |
| Goal-Driven Execution | **Verify Before Claiming Done** | Evidence before assertions. Contract tests, freshness checks, loud failures. Never claim "done" without running verification. |
| *(new)* | **Evidence Over Assumptions** | Tag confidence [empirical/predicted/speculative]. Predicted claims get expiration. Source of truth > copies. Never fabricate. |
| *(new)* | **Foundation First, Then Skills** | Pixar Brain Trust pattern. Build shared context before features. Updates compound across all skills. |
| *(new)* | **Coordinate Across Agents** | Lock files, handoff signals, MODE flags, scope boundaries. Born from real multi-agent failures. |

## The 7 Principles (summary)

| # | Principle | One-line test |
|---|---|---|
| 1 | **Intent Before Implementation** | Can you state the mission in one sentence? If not, stop and clarify. |
| 2 | **Evidence Over Assumptions** | Is this claim tagged [empirical], [predicted], or [speculative]? |
| 3 | **Minimum Viable Architecture** | Would a senior engineer say this is overcomplicated? |
| 4 | **Surgical Precision** | Does every changed line trace to the user's request? |
| 5 | **Verify Before Claiming Done** | Did you run the check and read the output before claiming success? |
| 6 | **Foundation First, Then Skills** | Did you load the context before producing the output? |
| 7 | **Coordinate Across Agents** | Did you check for locks and signal your intent? |

Full details in [`CLAUDE.md`](CLAUDE.md). Skill version in [`skills/karpathy-guidelines/SKILL.md`](skills/karpathy-guidelines/SKILL.md).

## Usage

### As a CLAUDE.md (simplest)

Copy `CLAUDE.md` into your project root. Claude Code reads it automatically.

### As a Claude Code skill

```bash
# Copy the skill into your project
cp -r skills/karpathy-guidelines .claude/skills/intent-driven-building
```

### As a Claude Code plugin

Install from the `.claude-plugin/` directory for global availability across all projects.

## Origin Story

These principles were codified during a 12-hour build session where three Claude Code sessions on two machines built, tested, and validated a multi-agent content production system from scratch. The coordination failures, evidence gaps, and foundation-loading problems encountered during that build became principles 5, 6, and 7.

Karpathy's principles (1-4) are necessary but not sufficient when:
- Multiple AI agents operate on the same project simultaneously
- The AI needs project-specific context (audience, voice, positioning) to produce non-generic output
- Claims need to be grounded in evidence, not training-data averages
- Work needs to persist and hand off across conversation boundaries

## Attribution

- **Karpathy's 4 principles:** [Andrej Karpathy (@karpathy)](https://x.com/karpathy/status/2015883857489522876)
- **Original skill implementation:** [forrestchang/andrej-karpathy-skills](https://github.com/forrestchang/andrej-karpathy-skills)
- **Intent-driven extension:** David Marshall / TheAgileMind

## License

MIT (same as upstream)
