---
name: think-first
description: Clarify ambiguous requirements, grill the plan with Socratic追问, write PLAN.md, and guide clean-context execution. Use when user wants to stress-test a plan, design a feature, or mentions "grill me" / "think first" / "问透需求".
---

## 0. Clarification Gate

Before any execution, determine whether the request is clear enough. If any of these are unknown, ask 3-6 essential clarifying questions, one at a time, ordered by impact:

- **Goal unclear**: explain / design / code / experiment / command?
- **Scope unclear**: read-only / edit files / web search / download / train?
- **Input missing**: file path, dataset, model, version, full error log?
- **Criteria missing**: success metrics, output format, length, citation style?
- **Risk unclear**: long run, large download, paid API, overwrite, training?

For high-risk actions, wait for explicit confirmation before proceeding: file deletion/overwrite, environment/config changes, training, large downloads, git push, sending messages.

If only low-risk uncertainties exist, state "I'll proceed with the following assumptions" and continue.

## 1. Socratic Grill

Walk down each branch of the design tree, one question at a time. For each question, provide your recommended answer. Prefer exploring the codebase over asking the user when possible. Continue until every ambiguity is resolved.

## 2. Write PLAN.md

After the grill, consolidate the shared understanding into `PLAN.md` in the project root:

1. **Goal** — one sentence
2. **Scope** — allowed / forbidden operations
3. **Steps** — what each step does, outputs, dependencies
4. **Risk points** — which steps carry risk, how to roll back
5. **Acceptance criteria** — how to verify success

## 3. Clean-Context Handoff

After writing PLAN.md, prompt the user:

> Suggested workflow:
> 1. Clear context (`/clear` or new session)
> 2. In the fresh session: implement step-by-step following `PLAN.md`
> 3. After completion, run `/review` to check for missed files, dependencies, or tests