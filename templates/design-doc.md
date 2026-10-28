# Design Document — <project name>

Version: 0.1 (<YYYY-MM-DD>) · Status: draft

> One design document per project, kept up to date **in the same change** that alters the design. Create every chapter now. A chapter that does not apply says "N/A (reason)". A chapter not yet started says "Not started". Never leave a chapter missing — a missing chapter is where the agent hides the thing it did not think about.

| Ch. | Content | Status (not started / in progress / reviewed) |
|---|---|---|
| 1 | Overview | not started |
| 2 | Requirements | not started |
| 3 | Concept design | not started |
| 4 | Operation (user-facing behaviour) | not started |
| 5 | External interfaces | not started |
| 6 | Internal interfaces | not started |
| 7 | Module structure | not started |
| 8 | Detailed design | not started |
| 9 | Tests | not started |
| 10 | Troubleshooting log | not started |
| 11 | Change log | in progress |

Design order: **data/content → functions → UI**. Decide what goes in, what comes out and what is stored before deciding how it is processed, and decide the screens last. Starting from the UI is how you discover missing data at the end.

---

## 1. Overview
Purpose, background, scope, terms, related documents.

## 2. Requirements
Every requirement gets an ID. Every ID gets at least one test in chapter 9 (see `requirements-test-matrix.md`).

| ID | Requirement | Test ID(s) |
|---|---|---|
| R1 | | T? |

**Out of scope (with reasons)** — copy from the plan and keep in sync:

| Item | Reason |
|---|---|
| | |

## 3. Concept design
Compare the options, state what you chose and why, and **keep the rejected options with the reason for rejecting them**. Future-you will ask.

| Option | Description | Decision / reason |
|---|---|---|
| A | | rejected: … |
| B | | **chosen**: … |

## 4. Operation
What the user does, what they see, the flow of a typical session. Written after chapters 2–3, not before.

## 5. External interfaces
Other devices, users, connectors, protocols, file formats. Anything that crosses the project boundary.

## 6. Internal interfaces
Functions, signals, data structures between modules.

## 7. Module structure
Block diagram, responsibility of each module, dependencies.

## 8. Detailed design
Circuits, mechanics, software — the detail. Split into separate files if it grows.

## 9. Tests
Reference the test specification and the results. Rule: **"not run" is written as "not run", never as "pass".**

## 10. Troubleshooting log
Symptom → cause → fix. Every defect found goes here, including the ones the agent caused. Reusable lessons are copied to `lessons-learned.md`.

## 11. Change log

| Date | Chapter(s) | What changed and why |
|---|---|---|
| <YYYY-MM-DD> | all | Document created with all chapters |

---

Rules for the agent:
- If the code or drawing disagrees with this document, do not silently pick one. Ask which is correct, then fix the other.
- Anything unverified is written as "unverified" or "TBD". Do not fill gaps with plausible text.
- When a decision is made or changed, update the chapter **and** the change log in the same piece of work. "Later" means never.
