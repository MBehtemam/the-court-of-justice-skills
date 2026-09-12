# CONTEXT

Glossary of the ubiquitous language for the court-of-justice skills.

## Court

A single convening of a jury to answer one Question. Not a persistent institution — each invocation is its own court.

## Question

The matter put before the jury by the Judge. Domain-agnostic: may come from any field (engineering, medicine, writing, …) and may be multiple-choice or open-ended.

## Jury

The panel of Jurors empaneled for one Court. Jurors may or may not disagree; disagreement is signal, not failure.

## Juror

One independent agent on the panel, ideally backed by a model different from the other jurors'. Which models are available depends on the harness the court runs in; the roster is discovered at runtime, not hard-coded.

## Ballot

A single Juror's answer to the Question: their position, reasoning, and vote. Cast blind by default — a juror does not see other ballots before casting.

## Debate Round

An optional, short second phase: jurors see each other's ballots and may change their vote. Always preceded by blind independent ballots. Whether to hold one may be put to the human.

## Verdict

The collected ballots and tally returned to the Judge. A split (hung jury) is a valid verdict — it informs rather than blocks.

## Judge

The parent agent that convened the court **together with** the human. There is no separate judge agent: the invoking agent aggregates, and the human decides. When no human is in the loop, the invoking agent acts on the verdict alone.
