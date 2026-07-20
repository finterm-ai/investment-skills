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

Use the [`skills` CLI](https://github.com/vercel-labs/skills), which installs into
whichever agent directories it detects:

```bash
npx skills add finterm-ai/skills                       # choose interactively
npx skills add finterm-ai/skills --skill buffett-investment-framework --yes
```

Add `-g` to install for your user instead of the current project, `--copy` to install an
independent snapshot rather than a symlink, and `--list` to see what a repository offers
without installing it.

For automation, pin both the installer and the source commit so a run installs exactly
the code and content you reviewed:

```bash
npx --yes skills@1.5.14 add \
  https://github.com/finterm-ai/skills/tree/f844999a3d73ad8c0b36573c5c4ccf2e795d7e49 \
  --skill buffett-investment-framework --copy --yes
```

To install without the CLI, copy the skill folder into the directory your agent reads.
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

Either way the installed folder is self-contained: a `SKILL.md`, its reference modules,
and a standard-library runtime script, with no network, database, or package-manager
dependency. Verify an installed copy at any time:

```bash
python3 <skills-dir>/buffett-investment-framework/scripts/framework.py validate
```

## License

MIT — see [LICENSE](LICENSE). The skills provide analytical guidance, not buy, sell,
hold, position-size, or trade instructions, and each documents its own limits.
This project is not affiliated with, approved by, or endorsed by Warren Buffett or
Berkshire Hathaway.
