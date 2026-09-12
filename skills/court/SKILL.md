---
name: court
description: Convene a jury of independent agents to answer one question, and return their ballots verbatim. Use when a decision is hard enough to be worth more than one opinion, when you want to know whether independent reasoners agree, or when the user asks to convene a court, empanel a jury, or put something to a vote.
---

Put one **Question** to a panel of independent **Jurors** and bring back what they said. You are not the jury — you are the Judge, together with the human. Your job is to ask well, stay out of the answers, and show the human the ballots.

**Classify the Question.** Multiple-choice if it offers options, open-ended otherwise — a near-mechanical read of its surface, not a judgement on the merits. Write it once, in full, and send every juror that same text. No angles, no personas, no "you are the skeptic": an assigned stance manufactures the disagreement the court exists to measure.

**Empanel an odd number** — three unless the Question is genuinely hard. Above four jurors, ask the human first; that is real money. Jurors must not see each other's ballots, so dispatch them in parallel and never relay one juror's answer to another.

**Vary what backs them where you can.** Use your subagent mechanism's per-agent model setting if it has one; otherwise shell out to whatever sibling CLIs are installed (`claude -p --model`, `opencode run -m`, `codex exec -m`, `gemini -p -m`, `cursor-agent -p --model`, `copilot -p --model`, `ollama run`) — one juror each, in parallel. If only one model is reachable, still empanel independent jurors, and **say so in the verdict**: same-model agreement is weak evidence of anything.

Instruct each juror to answer and nothing else — no editing, no tools, no recommendations to you — in exactly this block:

```
🗳️ **<juror>** — **VOTE: <the chosen option, or a one-line answer>**

**Reasoning:** <why>
**Trade-offs:** <what it costs — or, for a multiple-choice Question, why not the others>
```

A juror may reject the framing outright: if the options are all bad or the Question is wrong, saying so is a valid ballot, not a failed one.

**Report the ballots verbatim.** Every one, in full, to the human — your summary is not a substitute for them. Table them only when the answers are commensurable, which in practice means the multiple-choice case; open-ended answers usually sit on different axes, and the first thing a cell truncates is the reasoning. Do not tally, do not call a split a hung jury, and never convene a second round to break a tie: a split is a valid verdict.

Then give your own read as the Judge — clearly marked as yours, after the ballots, never in place of them. The human decides. You are done when the ballots are in front of them.
