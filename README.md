# agent-skills

Agent skills I use every day, in the open [Agent Skills](https://agentskills.io) format.
They work in Claude Code, Codex, Cursor, Gemini CLI, OpenCode, and other agents that read `SKILL.md` files.

## Install

```sh
npx skills add fquresh/agent-skills
```

To install by hand, copy a folder from `skills/` into your agent's skills directory.
For example, use `~/.claude/skills/` or `~/.agents/skills/`.

## Skills

| Skill | What it does |
| --- | --- |
| [deepen-prompt](skills/deepen-prompt/SKILL.md) | Rewrites a broad prompt so it asks for deeper work, not more work. |
| [plain-language-breakdown](skills/plain-language-breakdown/SKILL.md) | Breaks a dense source into fixed layers you can recall with the source closed. |
| [market-positioning-read](skills/market-positioning-read/SKILL.md) | Turns a market headline into a sourced positioning read with bull and bear cases per stock. |

## deepen-prompt

Most prompts ask an agent to do more.
This skill makes the agent do the task the way an expert in the field does it.

Invoke it with your prompt:

```
/deepen-prompt our web app feels slow lately, figure out why and make it faster
```

The agent does not do the task.
It answers four questions first:

1. What would a top professional do that the prompt does not ask for?
2. What is the rawest material they would start from?
3. What specific methods and tools would they use?
4. What, other than the agent or the user, would show the result is correct?

Then it rewrites the prompt to ask for exactly that, at the same scope or smaller.

### Example

Original prompt:

```
our web app feels slow lately, figure out why and make it faster
```

Some of the pre-flight answers:

- **Professional moves:** prove the slowdown is a real regression before any code changes. Define "slow" as p75 LCP or p95 API latency, not as an average. Find the start date and match it to deploys.
- **Raw material:** real-user monitoring data, server access logs, the database slow query log, and lockfile diffs across the regression window.
- **Methods:** change-point detection, `git bisect` with a scripted performance test, WebPageTest waterfalls, and `EXPLAIN ANALYZE`.
- **Independent validation:** 7 days of real-user field data back at the baseline, and a canary that beats the control group.

The rewritten prompt (shortened):

```
Goal: Find the root cause of the recent slowdown and ship the smallest fix
that brings user-facing latency back to its earlier baseline.

Approach:
1. Confirm the regression is real. Define "slow" as a specific metric.
   If there is no measurable regression, stop and report that.
2. Find the start date. Match it to deploys, dependency bumps, and data growth.
3. Break the latency into layers and make a latency budget table.
4. Fix the largest contributor first. Measure again before the next fix.

Validation (required):
- Write down the target number before the fix.
- Compare a canary against control on server p95 duration.
- Check 7 days of real-user data against the pre-regression baseline.

Depth over breadth. Do not add scope beyond this.
```

### Credit

The four questions come from Felix Rieseberg's essay [How to be more ambitious: A tutorial for humans with models](https://felixrieseberg.com/how-to-be-more-ambitious-a-tutorial-for-humans-with-models/).
The skill quotes his prompt with credit.
The MIT license covers the rest of this repo, not his text.

## plain-language-breakdown

A summary compresses a dense source.
This skill builds a scaffold instead, so you can explain the source with it closed.

```
/plain-language-breakdown https://en.wikipedia.org/wiki/Basel_III
```

The output always has the same 8 layers:

| Layer | What it gives you |
| --- | --- |
| 0. The one line | What this is, in 20 words or fewer. You can stop here. |
| 1. The problem it solves | Why the thing exists, in 3 sentences or fewer. |
| 2. The story, in order | A numbered causal chain, one idea per line. |
| 3. The shape | Counts and structure, and what not to memorise. |
| 4. The words you need | A glossary with plain meanings and everyday analogies. |
| 5. What is being claimed | Fact, interpretation, and hypothesis, kept apart. |
| 6. How I would know I am wrong | What kills the claim, what confirms it, and what is unverified. |
| 7. Closed-book test | 5 questions to answer without the source. |

## market-positioning-read

A market headline is not a trade.
This skill finds the primary source behind a post and checks recent price action.
Then it gives a bull and bear case for each affected stock.

```
/market-positioning-read https://t.co/<link to a news post>
```

The agent works in six steps:

1. Follow the link to the original article, filing, or transcript.
2. Find where the post's framing differs from the source, for example volume vs price.
3. Pull recent price action, guidance, and dated third-party data.
4. Find the second-order signal: who gains pricing power, and who absorbs the cost.
5. Write a short bull and bear case for each name, with a sourced number in each.
6. Give a positioning table, pair ideas, the main risk, dated catalysts, and the limits of the read.

See [a filled example](skills/market-positioning-read/references/example-memory-ltas.md).

## License

[MIT](LICENSE)
