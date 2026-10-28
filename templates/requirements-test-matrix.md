# Requirements ↔ Test Matrix — <project name>

Version: 0.1 (<YYYY-MM-DD>)

> Decide the test method **before** the design review, not after the implementation. This is what turns an agent's "it works" into "which tests, under which conditions, how many passed".

## Rules

1. **Every requirement has at least one test.** A requirement that cannot be tested is either rewritten until it can be, or marked "not testable" with the reason and the alternative check (review, inspection, calculation).
2. **Pass criteria are numbers.** Not "fast enough" but "≤ 200 ms at 95th percentile over 100 runs". Not "stable" but "0 resets in 24 h".
3. **Method is one of:** real hardware / simulation / test jig / desk check (review, calculation).
4. **Level is one of:** unit (part, module) / integration (between modules, with external devices) / acceptance (whole product).
5. **"Not run" is a status, not a pass.** The agent never writes "pass" for something it did not execute, and never writes "should pass".
6. **Results carry evidence:** measured value, date, conditions. Progress in the plan is computed from counts: `passed / total`.

## Matrix

| Req ID | Requirement (short) | Test ID | Test name | Method | Level | Conditions (equipment, environment, input) | Pass criterion (numeric) | When / who | Status | Result (value, date) |
|---|---|---|---|---|---|---|---|---|---|---|
| R1 | | T1 | | real hw | unit | | | | not run | |
| R2 | | T2 | | sim | unit | | | | not run | |
| R2 | | T3 | | real hw | integration | | | | not run | |

## Coverage check (the agent fills this in and keeps it true)

- Requirements with no test: `<list IDs or "none">`
- Tests with no requirement (scope creep?): `<list IDs or "none">`
- Pass criteria that are not numeric: `<list IDs or "none">`
- Summary: `passed <n> / failed <n> / not run <n> / total <n>` → plan progress for the test task = passed / total

## On failure

A failed test goes to the design document's troubleshooting log (symptom → cause → fix) before it is re-run. A test is not "flaky"; it is a defect in the product, the test, or the understanding of the requirement, and the log says which.
