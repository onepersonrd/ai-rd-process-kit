# Project Plan — <project name>

Version: 0.1 (<YYYY-MM-DD>) · Overall progress: **0%** (weighted average of the task table)

> Who fills this in: the AI drafts, the human decides. Nothing below "1. Scope" is implemented until the human has read and accepted sections 1–3.

## 1. Scope — decide this before planning anything

| Item | Your answer (1–2 lines each; do not skip) |
|---|---|
| **Constraints** | Effort (person-days), budget, deadline, who is responsible |
| **Vision** | The ideal end state, in a few lines |
| **First release** | What ships first. The difference from the vision goes to "Deferred" below |
| **Core concept (one sentence)** | "For <who>, solves <what problem>." If it does not fit in one sentence, the scope is still too wide. "For everyone" is not an answer |
| **Out of scope** | What you will *not* build, and why. Writing "no" is also design |
| **MVP** | The smallest form in which the core concept delivers value. Not "the full thing minus features" |
| **Deferred** | What moves to later releases, and the path from the MVP to it (1–3 lines) |

Unknowns that affect feasibility: mark them "unverified" and add a task to find out. Never fill them with a guess.

## 2. Completion criteria

Write these **before** the task list. They must map to the requirements (e.g. "all tests for R1–R12 pass").

- [ ] …
- [ ] …

## 3. Tasks

| ID | Task | Deliverable / done when | Owner | Due | Weight | Progress % | Status |
|---|---|---|---|---|---|---|---|
| T1 | | | | | 1 | 0 | not started |
| T2 | | | | | 1 | 0 | not started |

Weight = effort estimate (person-days). If you cannot estimate, use equal weights and say so here: `Weights: equal (not estimated)`.

### Progress scale — the number means exactly this

| % | Meaning |
|---|---|
| 0 | Not started |
| 25 | Started, in progress |
| 50 | Draft complete, not yet self-checked |
| 75 | Waiting for review, or under test |
| 100 | **Accepted in review AND tests passed** (where tests apply) |

Rules the agent must follow:
- 100% is only for items that meet the completion criteria. Nothing unverified is "almost done"; it stays at 75.
- Where things can be counted, count them: `tests passed 38 / 52 → 73%`.
- Show the gap between planned and actual progress. Do not hide a delay.

## 4. Milestones

| Date | Milestone |
|---|---|
| | Design review (scope, requirements, concept, test method accepted) |
| | Prototype complete |
| | Release |

## 5. Risks and assumptions

- Parts / dependencies / third-party work that can block you:
- Things you assumed but have not verified:

## 6. Update log

Update at every stopping point, at the end of every work session, and at least daily. When the plan changes, do not delete — write `before → after, reason`.

| Date | Overall % | What changed |
|---|---|---|
| <YYYY-MM-DD> | 0% | Plan created |
