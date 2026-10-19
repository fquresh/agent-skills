---
name: plain-language-breakdown
description: Break a dense source into a fixed, layered explanation the reader can reproduce with the source closed. Use when the user pastes, links, or names a paper, filing, report, research note, or long thread and asks to understand it, says it is hard to follow or a wall of text, or asks for a summary of material they must act on. Delivers a breakdown, not a summary. Do not use for source code, changelogs, or quick factual lookups.
argument-hint: <the source text, a file path, or a URL>
---

# Plain-Language Breakdown

This skill turns a dense source into a fixed, layered breakdown.
The goal is understanding the reader can reproduce with the source closed.

## When to Use

- The user pastes, links, or names a dense source and asks to understand it.
- The user says a document is hard to follow, too technical, or a wall of text.
- The user asks for a summary of a paper, a filing, research, or a long thread. Deliver a breakdown instead of a summary.
- The user needs to build conviction on a position or a decision.
- Do NOT use for source code, changelogs, or quick factual lookups.

**Deliver a breakdown, never a summary.**
A summary compresses text.
A breakdown builds a scaffold the reader can hang new facts on.

## Why comprehension breaks (six joints)

Name the joint before writing.
A summary that misses the joint does not help.

| Joint | What goes wrong | Fix in the output |
|---|---|---|
| Vocabulary | Unknown terms eat working memory before meaning starts | Layer 4: glossary, with an everyday analogy |
| Scaffold | New facts have no hook to attach to | Layer 1: the problem the thing solves |
| Flat depth | Everything sits on one plane, so there is no place to stop | Layers 0-7: the reader stops at any layer |
| Truth status | Fact, opinion, and forecast are mixed together | Layer 5: three labelled buckets |
| No falsifier | No kill criteria, so only vibes, never conviction | Layer 6: what would prove this wrong |
| No recall test | Reading feels like knowing | Layer 7: closed-book questions |

## The output template (fixed, in this order)

```
# <Title> - Plain-Language Breakdown
> Source, source date, staleness warning.

## 0. The one line
<20 words or fewer. What this is.>
-> If you stop here, <what the reader now knows>.

## 1. The problem it solves
3 sentences or fewer. Why does this exist?

## 2. The story, in order
Numbered causal chain. One idea per line. No jargon.

## 3. The shape
Counts, sizes, structure. What must the reader hold in mind?
What should they NOT memorise?

## 4. The words you need
| Term | Plain meaning | Everyday analogy |

## 5. What is actually being claimed
- FACT (sourced and checkable):
- INTERPRETATION (someone's reading):
- HYPOTHESIS (a prediction, may be wrong):

## 6. How I would know I am wrong
- Kills it:
- Confirms it:
- UNVERIFIED / needs checking:

## 7. Closed-book test
5 questions. Answer with the source closed.
```

When the breakdown goes to a file, start from the blank copy in `references/template.md`.

The header line records the source, its date, and how current it is.
If the source has no date, write "undated" and say what in it could have changed since.
If you only saw a summary or an excerpt of the source, say so in the header.

## Rules

1. One idea per line. Never two ideas in one sentence.
2. Define a term before you use it. First use gets the plain word.
3. Layer 0 is the triage gate. The reader must be able to stop there.
4. Layer 5 never mixes buckets. A fact with a forecast attached is two entries.
5. Quote the source's own numbers. Never present an invented number, name, or result as the source's. Inputs for a worked example are allowed only when labelled "illustrative, not from the source".
6. Mark anything you inferred as UNVERIFIED. Say what would settle it.
7. "One idea per line" applies to prose lines. A glossary cell can hold a meaning and an analogy.

## Get the raw source first

Read the full source text, not a summary of it.
If a fetch tool returns only a model summary, try a raw text or download route before you write.
If you still cannot get the full text, the header must say so.
Then mark every number from the summary as UNVERIFIED.

## When the source is a wall of text

This is the common failure: a good document stored as one paragraph.

1. Count the distinct ideas first. If there are more than about 10, state the count at the top of Layer 2.
2. Find the spine. Group the ideas into 3-6 blocks and name each block.
3. Tell the reader what NOT to memorise. This is often the most useful line.
4. Write Layer 0 before anything else. It forces the spine to surface.

## When the source is one hard concept

This mode can combine with the wall-of-text mode. A long page about one idea uses both.
Keep the layer order.
Layer 2 becomes the mechanism chain: inputs to process to output.
Add a worked example with real numbers.

## Conviction rule (decision and investment material)

Conviction is not agreement.
Conviction is the ability to state the mechanism and the falsifier in your own words.
Use this rule only when the user must decide or act on the material.
Skip it for a request that is only about learning.
When it applies, add these three questions to Layer 6:

- What would make me reverse this decision?
- What is the cheapest way to be wrong here?
- Which claims are FACT, and which are someone's hope?

## Pitfalls

- Do not skip the glossary because a term looks obvious. Domain terms are the usual block.
- Do not write more than 3 sentences in Layer 1. Length here means the spine is unclear.
- Do not bury the falsifier. It gets its own numbered layer.
- Do not pad with the source's own hedging. Cut it and keep the fact.
