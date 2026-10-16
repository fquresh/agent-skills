---
name: deepen-prompt
description: Rewrite a broad task prompt so it asks for deeper work, not more work. Use when the user asks to deepen, sharpen, or rewrite a prompt, asks "what would a top professional do here", or asks for a deeper version of a task. Runs a four-question pre-flight (professional moves, raw material, methods and tools, independent validation), then returns a rewritten prompt. Do not use it to do the task itself.
argument-hint: <the original prompt, or a file path that contains it>
---

# Deepen prompt

The user wants a deeper version of a task, not a bigger one.
The output is a pre-flight analysis and a rewritten prompt.
Do not do the task itself.

The skill comes from this source prompt.
If a later section conflicts with it, the source prompt wins.

> I want a deeper version of this task, not a bigger one.
> Before rewriting it: (1) say what a top professional in this field would do here that I'm not asking for; (2) name the rawest material they would start from instead of what has already been digested for me; (3) name the specific methods and tools they would use; (4) say what, other than you or me, would show the result is right.
> Then rewrite my prompt to ask for exactly that.

Source: Felix Rieseberg, "How to be more ambitious: A tutorial for humans with models" (https://felixrieseberg.com/how-to-be-more-ambitious-a-tutorial-for-humans-with-models/).

## Step 1: Identify the decision, the field, and the professional

State the decision or action the work must support, in one line.
If the original prompt gives no decision, write your best guess and mark it as an assumption.
Name the field in one line.
Name the role of the person who does this work at the highest level for a living.
If the task spans fields, name one professional for each field.

## Step 2: Answer the four questions

Write each answer as a short bulleted list.
Each bullet is one concrete move, not a category.
A category is "check data quality".
A move is "reconcile row counts against the source export".

1. **What would a top professional do that the prompt does not ask for?**
   Look for the assumption the prompt takes as true without proof.
   Look for the negative case, the cost side, and the failure mode.
   Look for the base rate or the reference class.
   Look for the other parties who are affected, and their incentives.
   Look for a small, cheap test before a large commitment.
   Look for legal, regulatory, safety, or platform-rule exposure.
2. **What is the rawest material they would start from?**
   Prefer primary sources to summaries, dashboards, and secondary articles.
   Name the actual documents, datasets, records, source code, logs, or people.
   If you are not sure a named source exists, mark it as unverified.
3. **What specific methods and tools would they use?**
   Name real tools, techniques, and analytic methods.
   Connect each one to a step in the work.
   Prefer the simplest method that answers the question.
4. **What, other than the agent or the user, would show the result is correct?**
   The check must be independent of the work and of the agent that did it.
   Examples: reconciliation against a separate system, agreement with a third-party source, a prediction tested on held-out data, a live result inside a predicted range, review by a named type of outside expert.

## Step 3: Rewrite the prompt

The rewrite asks for exactly the four answers from Step 2, and nothing more.
Put the rewrite in a fenced code block so the user can copy it.
This structure usually works. Drop a part if the task does not need it.

- Goal: one sentence that names the decision the work supports.
- Scope: what is in and what is out.
- Starting material: the sources from question 2, with a fallback if access is not available.
- Approach: the moves from question 1 and the methods from question 3.
- Validation: the checks from question 4, as required steps.
- Deliverables: what the work returns.
- Last line: "Depth over breadth. Do not add scope beyond this."

## Rules

- Keep the scope the same size as the original, or smaller.
- A person who did not do the work must be able to do each validation check.
- If the premise of the prompt is false by simple arithmetic or known evidence, say so in question 1. Make the rewrite require that check first.
- Do not research the topic to answer the task. A short lookup to confirm that a named source or tool exists is permitted.
- Ask the user one question only if the decision in Step 1 is unclear and a guess would change the rewrite materially.
