---
name: arena
description: >-
  Make 100 versions of the agent fight to the death over one task. Spins up N
  sub-agents (default 100, --quick for 16), gives every one the exact same
  task plus a different strategy card (reasoning mode, workflow, strategy),
  then runs a single-elimination bracket: they attack each other's solutions,
  defend and revise, and a judge scores every match on a written rubric until
  one solution survives. Use when the user is not satisfied with an answer,
  calls it a bad answer, says try again or do better, says "arena", says
  "aplicar el skill", asks to apply this skill, or asks to make them compete.
---

# arena

Cursor entry point for the arena skill in this repository.

Read `skills/arena/SKILL.md` and follow it exactly. That file is the whole procedure, including the prompt templates. `bracket.py` reads those templates from that same file.

From the repository root, `ARENA` means:

```bash
python3 skills/arena/bracket.py <command>
```

Run every `ARENA` command from the repository root, so `.arena/LATEST` is created there. In Cursor, spawn each sub-agent with the Task tool: `subagent_type` `general-purpose`, `description` `arena <job id>`, `prompt` set to the one line the procedure specifies, `run_in_background` false.
