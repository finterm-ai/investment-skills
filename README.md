# Finterm Skills

Agent skills from [finterm.ai](https://finterm.ai) for financial analysis.

Each skill in this family packages knowledge that was mined from primary sources and
then consolidated, cross-checked, and reviewed with Finterm’s analysis tooling, so an
agent can apply it without loading the underlying corpus.

## Skills

One skill is published today; the family may grow.

| Skill | What it does |
| --- | --- |
| [buffett-investment-framework](buffett-investment-framework/) | Applies a 65-card framework distilled from Warren Buffett’s and Berkshire Hathaway’s published writings — his investment frameworks and mental models — to financial analysis, investment-memo review, and thesis evaluation. Read the [full introduction](docs/buffett-investment-framework.md). |

## Install

Copy a skill folder into the skill directory your agent reads.
From this repository’s root:

```bash
# Cross-agent project install (Codex, Cursor, and pi read this path natively)
mkdir -p your-project/.agents/skills
cp -R buffett-investment-framework your-project/.agents/skills/

# Claude Code
mkdir -p your-project/.claude/skills
cp -R buffett-investment-framework your-project/.claude/skills/

# Codex
cp -R buffett-investment-framework "${CODEX_HOME:-$HOME/.codex}/skills/"
```

Each skill folder is self-contained: a `SKILL.md`, its reference modules, and a
standard-library runtime script, with no network, database, or package-manager
dependency.

## License

MIT — see [LICENSE](LICENSE). The skills provide analytical guidance, not buy, sell,
hold, position-size, or trade instructions, and each documents its own limits.
This project is not affiliated with, approved by, or endorsed by Warren Buffett or
Berkshire Hathaway.
