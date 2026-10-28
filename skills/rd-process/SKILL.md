---
name: rd-process
description: Run a product-development task through the three-document gate (plan, design doc, requirements↔test matrix) and the lessons-learned loop. Use when the user starts a new project or feature, asks to "plan this", "write the spec", "set up the project", "update progress", "where are we", or when the agent has made a mistake that should be logged. Also use at the start of a session to read the plan and lessons before touching code.
---

# R&D process skill — three documents, one gate, one memory

This skill makes an AI coding agent work the way a careful one-person R&D shop works: decide scope first, write the plan / design document / test matrix, get them accepted, then build in small checked steps, and record every failure so it is not repeated.

## 0. Session start (every time)

1. Read `docs/plan.md` (if it exists): completion criteria, task table, latest update-log entry.
2. Read `docs/lessons-learned.md`: the patterns listed there are the mistakes you are most likely to make today.
3. Tell the user in two lines: current overall %, what the next task is. Then wait for instructions.

If the documents do not exist, go to step 1.

## 1. New project or feature → create the three documents

Do this **before** writing any code, schematic or layout. Small tool? Still do it; keep it short.

1. Copy the templates from this kit into `docs/` if they are not there:
   `plan.md`, `design-doc.md`, `requirements-test-matrix.md`, `lessons-learned.md`.
2. **Plan, section 1 (Scope):** draft the seven items from what the user said. Where the user has not decided, write `TBD — needs your decision` instead of guessing. Write the core concept as one sentence; if you cannot, say the scope is too wide.
3. **Plan, section 2 (Completion criteria):** write them before the task list, mapped to requirement IDs.
4. **Design doc:** create *all* chapters now. Fill 1 (overview), 2 (requirements with IDs), 3 (concept options with rejected ones), 9 (reference to the test matrix). Mark the rest "Not started" or "N/A (reason)". Design order: data → functions → UI.
5. **Test matrix:** one or more tests per requirement, numeric pass criteria, method and level. Fill the coverage check honestly.
6. Optional but recommended for hardware and anything you may publish: add a short "prior art / IP check" note to the plan — what was searched, what was found, whether anything blocks you. Flag "not done" if you skipped it.
7. **Stop and ask for review.** Present the scope table, the completion criteria and the test matrix. Do not start implementation until the user accepts them. In the acceptance message, confirm what is *out* of scope.

## 2. During the work

- Take the next task from the plan. Do one task (or one small piece of it). Report. Wait.
- Update the task's progress % using the scale in the plan. Never set 100 yourself; 100 is the user's call after review and tests.
- When a decision changes the design, update the design-doc chapter and its change log in the same step.
- When you need a fact (a part's pin, an API's behaviour, a rule, another project's state), open the source and cite it. If you cannot, write "unverified" and say what you would need.
- If the request grows beyond the plan, say "this is outside the current scope" and propose a plan change (before → after, reason). Do not just do it.

## 3. Tests and results

- Run the tests from the matrix. Record measured values, date, conditions.
- Status is one of `pass` / `fail` / `not run`. Never report "should pass" or treat "not run" as pass.
- Recompute the coverage summary and set the test task's progress to `passed / total`.
- A failure goes to the design doc's troubleshooting log (symptom → cause → fix) before re-running.

## 4. When you fail or are corrected

Before doing anything else, append an entry to `docs/lessons-learned.md`:

```
## YYYY-MM-DD: What happened (one line)
- Situation:
- Cause:   (why *you* did it — not "the tool was wrong")
- Prevention: (a check you will run next time, stated so the user can verify you ran it)
```

If the cause matches an existing entry, say "repeat of <date> pattern" — repeats matter most.

## 5. Session end (every time)

1. Update the plan: task %, overall %, one update-log line (date, %, what changed).
2. Report in a few lines: what is done, what is **not** done or not verified, the next step, and anything waiting on the user.
3. Do not round up. "Mostly done" is 75.

## Things this skill never does

Publish, deploy, send messages, pay, accept terms, or delete irreversibly. It drafts and hands over.
