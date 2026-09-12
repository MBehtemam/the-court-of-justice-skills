<p align="center">
  <img src="assets/court-logo.jpeg" alt="The Court of Justice Skills" width="520">
</p>

<h1 align="center">The Court of Justice Skills</h1>

<p align="center">
  Agent skills for putting a hard question to a jury of independent agents — and seeing what they actually said.
</p>

---

## `court`

Some decisions deserve more than one opinion. `court` takes a single question, puts it to an odd-numbered panel of **jurors** — independent agents, backed by different models where your setup allows — and brings back every ballot verbatim.

It is deliberately small: one `SKILL.md`, no config, no servers. The skill is domain-agnostic. Jurors are asked questions from any field — an architecture call, a diagnosis, a hiring decision, the structure of a chapter — because the value is independent reasoning, not domain tooling.

### What makes it a court, not a poll

- **Blind ballots.** Jurors never see each other's answers, so agreement means something.
- **No assigned personas.** Nobody is told to be "the skeptic". An assigned stance manufactures the disagreement the court exists to measure.
- **Jurors may reject the question.** If the options are all bad or the framing is wrong, saying so is a valid ballot.
- **The ballots are the output.** You see them in full, not just a summary of them. The skill does not tally, does not declare a hung jury, and never re-runs the vote to break a tie — a split is a real answer about a genuinely split question.
- **You decide.** The agent gives its own read, clearly marked, *after* the ballots. The verdict informs the decision; it doesn't make it.

### Install

```bash
npx skills add MBehtemam/the-court-of-justice-skills
```

Works with any agent that supports the [Agent Skills](https://agentskills.io/specification) format — Claude Code, opencode, Cursor, Gemini CLI, Copilot CLI, Codex, Amp and others.

### Use

Ask your agent to convene a court:

```
/court Should we migrate the write model to Postgres, or stay on the event store?
```

...or just describe the decision and say you want a jury on it. Each juror returns one block:

```
🗳️ **Juror 2** — **VOTE: Stay on the event store**

**Reasoning:** The migration cost is front-loaded and the pain you describe is read-side...
**Trade-offs:** Postgres would have simplified reporting, and you keep carrying...
```

The agent hands you all of them, then its own read — in that order.

### A note on model diversity

A jury of three agents all backed by the same model is one model in a trench coat. Their agreement is much weaker evidence than it looks. `court` varies the backing model where your environment permits — native per-subagent model settings, or shelling out to whichever sibling CLIs you have installed — and tells you when it couldn't.

## Repo layout

```
skills/court/SKILL.md   the skill
CONTEXT.md              the ubiquitous language (Court, Juror, Ballot, Verdict, Judge)
docs/agents/            conventions for agents working in this repo
```

Design decisions are worked in the open as GitHub issues — see the [wayfinder map](https://github.com/MBehtemam/the-court-of-justice-skills/issues/1) for the route and the reasoning behind each call.
