# Signal Selection Skill

A Claude skill for generating and grading GTM buying signals using a four-type model: **Structural**, **Leading**, **Trigger**, and **Custom**.

## What It Does

Two modes:

- **Generate** — Paste a campaign brief, get a signal stack back. One signal per stage, capped at 4-6, with reasoning for each.
- **Check** — Paste your existing signals, get them graded. Mislabeled types get called out directly with fixes. Missing stages get flagged.

The skill enforces structural tests on every signal:
- **Date test** on triggers (can you put a date on a calendar?)
- **Composite test** on customs (fused vs. real composite)
- **Standing condition test** on structurals (true for months, true next quarter?)
- **Redundancy test** on all (what stage does this catch that the others don't?)

## The Model

| Type | Stage | Catches |
|---|---|---|
| **Structural** | *Could* | Standing condition — the company is able to need this |
| **Leading** | *Getting ready to* | Early internal motion — hiring, building, preparing |
| **Trigger** | *Now* | Discrete event opening a time-sensitive decision window |
| **Custom** | *Precisely* | Engineered logic that sharpens any of the above |

## How to Use

### Claude Code

Drop `SKILL.md` into your project's `.claude/skills/` directory (per-project) or `~/.claude/skills/signal-selection/` (global). Claude Code discovers it automatically.

```
# Per-project
mkdir -p .claude/skills/signal-selection
cp SKILL.md .claude/skills/signal-selection/

# Global (available in all projects)
mkdir -p ~/.claude/skills/signal-selection
cp SKILL.md ~/.claude/skills/signal-selection/
```

Then just tell Claude: "Here's my campaign brief — generate signals" or "Grade these signals."

### Claude Chat (claude.ai)

Paste the contents of `SKILL.md` into a Project's custom instructions, or paste it at the start of a conversation. Then use it the same way.

### Claude Co-Work

If the skill is deployed to a project's `.claude/skills/` directory, co-work agents pick it up automatically.

## Built With

This skill was developed using TDD for documentation ([superpowers:writing-skills](https://github.com/obra/superpowers)). Three pressure scenarios were tested at baseline (no skill), then with the skill, then refined through a refactor cycle to close loopholes in composite testing, cross-signal redundancy, and thin-brief handling.

## License

MIT
