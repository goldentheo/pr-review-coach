# PR Review Coach

An interactive skill that helps developers build PR review skills by walking them through real pull requests. Instead of showing answers upfront, it asks you to spot issues yourself — building pattern recognition and review muscle memory through practice.

Drop a GitHub PR link, and the coach walks you through it like a senior engineer doing a paired review.

## How It Works

```
You provide a PR link
        │
        ▼
  1. Context Briefing       → Understand the PR's purpose, scope, and risk level
  2. Your First Pass        → What do YOU notice before the coach says anything?
  3. Guided Walkthrough     → File-by-file review with progressive hints
  4. Severity Calibration   → Learn to distinguish blockers from nits
  5. Targeted Challenges    → Bug hunts, security checks, test gap analysis
  6. Coach Reveal           → See what a senior reviewer would catch
  7. Scorecard & Growth     → Track your strengths and get actionable tips
  8. Review Comment Draft   → Get a copy-pasteable GitHub review comment
```

## Quick Start

```
Review this PR with me: https://github.com/owner/repo/pull/42
```

Optional modifiers:

```
Review this PR with me, focus on security: https://github.com/owner/repo/pull/42
```

```
Review this PR with me, I'm a beginner: https://github.com/owner/repo/pull/42
```

## Installation

### Claude.ai (Skills Upload — Recommended)

The simplest way. Works with Free, Pro, Max, Team, and Enterprise plans.

1. Download the `pr-review-coach.zip` from [Releases](https://github.com/goldentheo/pr-review-coach/releases)
2. Go to [Customize > Skills](https://claude.ai/customize/skills) in Claude.ai
3. Click **"+"** → **"+ Create skill"** → **"Upload a skill"**
4. Upload the zip file
5. Toggle the skill on
6. Start a conversation with a PR link

> **Team/Enterprise:** Owners can provision this skill org-wide via [Organization settings > Skills](https://claude.ai/admin-settings/skills) so every developer on the team has access.

### Claude.ai (Project Custom Instructions)

If you prefer not to use the skills system:

1. Copy the contents of [`pr-review-coach/SKILL.md`](pr-review-coach/SKILL.md)
2. Create a new Claude Project
3. Paste it as a custom instruction
4. Start a conversation with a PR link

### Claude Code (CLI)

```bash
# Clone into your project's instructions directory
mkdir -p .claude/skills
cp -r pr-review-coach .claude/skills/pr-review-coach
```

Or reference it in your `CLAUDE.md`:

```
@.claude/skills/pr-review-coach/SKILL.md
```

### Cursor

1. Go to **Settings → Rules for AI**
2. Paste the contents of `pr-review-coach/SKILL.md`

Or place it in your project:

```bash
mkdir -p .cursor/skills
cp -r pr-review-coach .cursor/skills/pr-review-coach
```

### VS Code — GitHub Copilot (with Claude model)

```bash
mkdir -p .github/copilot
cp pr-review-coach/SKILL.md .github/copilot/pr-review-coach.md
```

### VS Code — Continue.dev (with Claude)

Use a `.continuerules` file in your project root:

```bash
cp pr-review-coach/SKILL.md .continuerules
```

Or add to `~/.continue/config.json`:

```json
{
  "models": [{
    "title": "Claude",
    "systemMessage": "<paste contents of SKILL.md>"
  }]
}
```

### Any LLM

Copy the contents of `pr-review-coach/SKILL.md` and use it as a system prompt.

## What You'll Practice

| Skill | What the coach looks for |
|-------|-------------------------|
| Bug Detection | Logic errors, edge cases, off-by-one, null handling |
| Security | Input validation, auth checks, injection, data exposure |
| Performance | N+1 queries, loops with I/O, missing pagination |
| Testing | Coverage gaps, missing edge cases, brittle assertions |
| Readability | Naming, complexity, duplication, structure |
| Architecture | Separation of concerns, coupling, right-layer placement |
| Severity Judgment | Knowing what's a blocker vs. a nit vs. praise |

## Repo Structure

```
pr-review-coach/
├── README.md                  ← You are here
├── LICENSE
├── CONTRIBUTING.md
└── pr-review-coach/           ← The skill (zip this folder for Claude.ai upload)
    └── SKILL.md               ← All instructions in one file
```

The skill is a single `SKILL.md` file inside a folder. This structure is compatible with Claude.ai's skill upload (zip the `pr-review-coach/` folder), Claude Code (copy the folder to `.claude/skills/`), and any other tool that reads markdown instructions.

## How It Teaches

The coach uses three techniques that mirror how senior engineers actually mentor:

**Socratic questioning** — For each area of concern, the coach asks a question before making a statement. "What happens here if the input is empty?" forces you to think before being told.

**Progressive hints** — If you're stuck, the coach doesn't dump the answer. It gives gentle direction first, then a specific pointer, then reveals and explains. Three levels, calibrated to how you're doing.

**Pattern naming** — When the coach identifies something, it gives it a name: "This is an N+1 query." Names stick. Next time you see a database call inside a loop, you'll recognize it.

## Portability

The entire skill is a **single markdown file**. It works anywhere that accepts custom instructions:

| Platform | Where to put it |
|----------|----------------|
| Claude.ai Skills | Upload as zip via Customize > Skills |
| Claude Projects | Custom instructions |
| Claude Code | `.claude/skills/` directory |
| Cursor | `.cursor/skills/` or Settings > Rules |
| VS Code Copilot | `.github/copilot/` directory |
| Continue.dev | `.continuerules` or config |
| Any LLM | System prompt |

## Contributing

PRs welcome! See [CONTRIBUTING.md](CONTRIBUTING.md).

If you use this skill and find patterns or situations it doesn't handle well, please open an issue — real-world feedback makes the coach better.

## License

MIT — see [LICENSE](LICENSE).
