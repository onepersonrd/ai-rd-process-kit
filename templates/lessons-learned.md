# Lessons Learned — <project or workspace name>

> **The agent writes this file. The human does not.**
> When the agent fails, is corrected, or discovers that something it stated was wrong, it analyses the cause itself and appends an entry — in the same session, before moving on. Other agents and future sessions read this file at startup so the same mistake is not repeated. The human's job is to say "that was wrong"; the agent's job is to work out why and write it down.

Entry format:

```
## YYYY-MM-DD: What happened (one line)
- Situation:
- Cause:
- Prevention:
```

Keep entries short, concrete and reusable. Name the *pattern*, not just the incident. If an entry is a repeat of an earlier pattern, say so — repeats are the most important signal.

---

## Example entries (generalized from real projects; replace with your own)

## 2026-10-04: Claimed a sibling project used the same part without opening its latest files
- Situation: Asked whether project B used the same connector as project A. Answered "yes, same part" from memory of an older document.
- Cause: Did not open project B's current BOM. Treated a plausible recollection as a fact.
- Prevention: Any statement about another project's current state cites the file and date it was read. No file, no statement.

## 2026-10-07: Described a part's functions without reading its datasheet, and the text spread into shared documents
- Situation: Wrote a paragraph about a part's interface and modes. Two of the modes did not exist on that part. The paragraph was copied into a spec and a team knowledge base.
- Cause: Generated technical detail from general knowledge of the part family. Second occurrence of the same pattern in three days.
- Prevention: Technical claims about a specific part require the datasheet open and the page/section cited. Shared documents are not updated with unsourced technical text.

## 2026-10-27: Reported "the rule does not exist" after searching a coding standard for two keywords
- Situation: Searched a coding standard for "prefix" and "naming", found nothing, and reported that no rule applied. The rule existed under different wording ("identifier conventions").
- Cause: Keyword hit ≠ reading the relevant chapter. "Not found" was reported as "does not exist".
- Prevention: Questions of the form "is there a rule about X" are answered by reading the relevant chapters, not by keyword search. Report "not found with search terms A, B; chapter not read" rather than "none".

## 2026-10-27: ERC passed, netlist had three shorts
- Situation: An auto-generated schematic passed the electrical rules check. The netlist showed a rotated protection diode shorting two supply rails, a pull-up routed onto a data line, and a duplicated reference designator.
- Cause: Treated ERC as sufficient. ERC checks pin types, not whether nets are connected to the right places.
- Prevention: After generating a schematic, export the netlist and check supply/ground separation, polarity of oriented parts, and duplicate designators with a script before any layout work.

---

## Entries

<!-- Append new entries below. Newest last. -->
