# Humanizer

An agent skill that removes signs of AI-generated writing. Plain Markdown, runs in any harness that supports skill-style instructions. 40 patterns, a tiered vocabulary reference, a no-fabrication rule, and a draft, audit, final loop.

## Install

Claude Code (personal skills):

```bash
git clone <this-repo> ~/.claude/skills/humanizer
```

Or copy the `humanizer/` folder into any project's `.claude/skills/` directory. The runtime artifacts are `SKILL.md` and `references/vocabulary.md`; there is no build step.

## Usage

```
/humanizer
[paste text]
```

```
Humanize the prose in docs/launch-post.md
```

To match your own voice, include 2-3 paragraphs of your writing as a sample; the skill calibrates to it (including your em dash habits) instead of producing generic "clean" output.

For always-on behavior (write clean the first time instead of cleaning up after), keep the skill loaded while drafting; it applies the same rules during generation.

## What it will not do

Rewrites never add facts, names, numbers, dates, or citations that are not in the source. Vague claims get plain restatements or cuts, not invented specifics.

## Credits

Merged from three MIT-licensed skills, keeping the strongest parts of each:

- [blader/humanizer](https://github.com/blader/humanizer): pattern catalog structure, no-fabrication rule, false-positive guardrails, voice calibration, invocation modes, audit loop
- [hardikpandya/stop-slop](https://github.com/hardikpandya/stop-slop): false agency, narrator-from-a-distance, binary-contrast taxonomy, pre-delivery quick checks
- [brandonwise/humanizer](https://github.com/brandonwise/humanizer): vocabulary tiers, triage weights, cadence tells, reasoning-chain and acknowledgment-loop patterns, always-on mode

Underlying pattern research: [Wikipedia:Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing) (WikiProject AI Cleanup).

MIT license.
