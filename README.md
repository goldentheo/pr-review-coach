# 🎓 PR Review Coach

An interactive skill that helps junior developers build PR review skills by walking them through real pull requests in a structured, conversational coaching session.

Instead of showing the answers upfront, the coach asks the developer to spot issues themselves — building pattern recognition and review muscle memory through practice.

## How It Works

```
You provide a PR link
        │
        ▼
  1. 📋 Context Briefing       → Understand the PR's purpose and risk
  2. 🔍 Guided File Walkthrough → Review diffs, spot issues yourself
  3. 🎯 Targeted Challenges     → Bug hunts, security checks, test gaps
  4. 🧑‍🏫 Coach Reveal           → See what a senior reviewer would catch
  5. 📊 Scorecard & Growth Tips → Track your progress
```

## Installation

### Claude (Projects / System Prompt)

1. Copy the contents of [`pr-review-coach.md`](./pr-review-coach.md)
2. Paste it as a **custom instruction** or **system prompt** in your Claude project
3. Start a conversation with a PR link

### Claude Code (CLI)

Place the file in your project's instructions directory:

```bash
# From your project root
mkdir -p .claude
cp pr-review-coach.md .claude/pr-review-coach.md
```

Or add it to your `CLAUDE.md` file:

```markdown
@pr-review-coach.md
```

### VS Code — GitHub Copilot (with Claude model)

1. Create the instructions directory in your repo:

```bash
mkdir -p .github/copilot
```

2. Copy the skill file:

```bash
cp pr-review-coach.md .github/copilot/pr-review-coach.md
```

3. Copilot Chat will automatically pick it up as custom instructions.

### VS Code — Continue.dev (with Claude)

1. Open Continue config (`~/.continue/config.json`)
2. Add the skill as a system message:

```json
{
  "models": [{
    "title": "Claude",
    "systemMessage": "<paste contents of pr-review-coach.md>"
  }]
}
```

Or use a `.continuerules` file in your project root:

```bash
cp pr-review-coach.md .continuerules
```

### Cursor (with Claude)

1. Go to **Settings → Rules for AI**
2. Paste the contents of `pr-review-coach.md`

Or place it in your project:

```bash
cp pr-review-coach.md .cursorrules
```

## Usage

Once installed, start a session by providing a PR link:

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

## What You'll Practice

| Skill | Description |
|-------|-------------|
| 🐛 Bug Detection | Spotting logic errors, edge cases, off-by-one errors |
| 🔒 Security Awareness | Input validation, auth checks, injection risks |
| ⚡ Performance | N+1 queries, unnecessary loops, missing pagination |
| 🧪 Test Thinking | Missing test cases, coverage gaps, test quality |
| 📖 Readability | Naming, clarity, code structure, duplication |
| 🏗️ Architecture | Separation of concerns, coupling, right-layer placement |

## Portability

The entire skill is a **single markdown file** (`pr-review-coach.md`). It works with any LLM tool that supports custom instructions or system prompts:

| Platform | Where to put it |
|----------|----------------|
| Claude Projects | Custom instructions |
| Claude Code | `.claude/` directory |
| VS Code Copilot | `.github/copilot/` directory |
| Continue.dev | `.continuerules` or config |
| Cursor | `.cursorrules` or settings |
| Any LLM | System prompt |

## Contributing

PRs welcome! See [CONTRIBUTING.md](./CONTRIBUTING.md).

## License

MIT — see [LICENSE](./LICENSE).