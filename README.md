# AI R&D Process Kit

**Three documents that keep an AI coding agent honest — plan, design doc, test matrix — plus a lessons-learned loop the agent writes itself.**

Built by a one-person R&D shop that ships hardware, firmware and software with AI agents doing most of the typing. Generalized so you can drop it into any project. Works with Claude Code out of the box (skill included); the templates and rules work with any agent that reads a Markdown instruction file.

## The problem this solves

AI coding agents are fast, and they fail in a specific way: they **extend the scope without asking**, **report "done" without running the test**, **state facts they did not check**, and **repeat the same mistake next session**. None of this is fixed by a better model. It is fixed by a process the agent cannot skip.

## The idea in one paragraph

Before any implementation, the agent writes three documents and the human accepts them: a **plan** (scope decided in seven lines, completion criteria first, tasks with a progress scale where 100% means *reviewed and tested*), a **design document** (every chapter created on day one, "N/A" written explicitly, rejected options kept), and a **requirements↔test matrix** (every requirement has a test, every pass criterion is a number, "not run" is never "pass"). During the work the agent builds in small checked pieces and updates the documents in the same change. When it fails, it writes the cause and the prevention into a **lessons-learned** file that it reads at the start of every session.

## What's inside

```
kit/
├─ templates/
│  ├─ plan.md                      scope, completion criteria, tasks, progress scale, update log
│  ├─ design-doc.md                11 chapters, status column, change log, design order
│  ├─ requirements-test-matrix.md  R-ID ↔ T-ID, method, numeric pass criteria, coverage check
│  └─ lessons-learned.md           the file the agent writes; four real examples included
├─ rules/
│  └─ CLAUDE.md.example            13 promises to put at the root of your project
└─ skills/
   └─ rd-process/SKILL.md          Claude Code skill: session start, create docs, work, test, log, session end
```

## Quick start (5 minutes)

1. Copy `templates/*.md` into `docs/` in your project.
2. Copy `rules/CLAUDE.md.example` to your project root as `CLAUDE.md` and edit the bracketed lines.
3. Claude Code users: copy `skills/rd-process/` into `.claude/skills/` (project) or `~/.claude/skills/` (global). Then say "plan this" or "set up the project".
4. Other agents: paste the contents of `SKILL.md` into your agent's instructions.
5. Tell the agent what you want to build. It should come back with the scope table and ask you to accept it **before** writing code. If it starts coding, the rules are not loaded.

## The progress scale (the part people copy first)

| % | Means |
|---|---|
| 0 | Not started |
| 25 | Started |
| 50 | Draft complete, not self-checked |
| 75 | Waiting for review, or under test |
| 100 | **Accepted in review and tests passed** |

Unverified work stays at 75. Counts are used where possible (`tests passed 38/52 → 73%`). Delays are shown, not hidden.

## Why these rules (short version)

| Rule | The failure it prevents |
|---|---|
| Scope in seven lines, one-sentence core concept | "Build the whole vision" → nothing ships |
| Completion criteria before tasks | "Done" means whatever the agent says it means |
| All design-doc chapters created on day one | The missing chapter is where the unconsidered risk lives |
| Rejected options kept | Re-litigating the same decision every month |
| Every requirement has a numeric test | "It works" |
| "Not run" ≠ "pass" | The most common agent lie, and it is not even a lie — it is optimism |
| Agent writes its own lessons | The same mistake, every new session |
| "Not found" ≠ "does not exist" | A keyword search reported as a fact |

## Who this is for

Solo developers and small teams building real products — especially where software meets hardware and a mistake costs a board spin, not a redeploy. If you work alone with an agent and have no reviewer but yourself, this is the reviewer's checklist.

## What this is not

Not a project-management tool, not a methodology with certification, not a prompt pack. Four Markdown files and a habit.

## Origin and disclosure

The templates are generalized from the working rules of a one-person R&D operation (small hardware products: boards, firmware, PC tools) that runs its development with Claude Code. The example lessons are real, with product names removed. This README and the templates were drafted with an AI assistant from the author's own work logs and published with the author's approval.

A paid companion pack (filled-in examples, the agent-failure checklist, the netlist and parts-availability checks, Japanese operating notes) is planned. The free kit stays free.

## License

MIT — see `LICENSE`. Use it in your projects, commercial or not. Attribution appreciated, not required.

---

日本語の説明は [README.ja.md](README.ja.md) にあります。
