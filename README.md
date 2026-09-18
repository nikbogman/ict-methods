# ict-methods

An agent skill for HBO-ICT research methodology, backed by the [ictresearchmethods.nl](https://ictresearchmethods.nl) standard (HBO-i's DOT framework, method catalogue, and research patterns). Three modes:

- **Lookup** — "what is A/B testing?", "what's it called when you compare your product against competitors?": returns the method's full card, no verdict or ranking.
- **Recommend** — you have a research question or activity but no method yet: matches it against the pattern navigator and ranks candidate methods by phase fit, with rationale and prerequisites.
- **Validate** — you've already picked method(s): checks they're recognized, fit their research phase, have their prerequisites covered, and combine into a known pattern.

It only runs when you explicitly type `/ict-methods` — it never auto-triggers on keywords in normal conversation.

## Layout

```
ict-methods/
├── SKILL.md
└── references/
    ├── index.md
    ├── dot-framework.md
    ├── research-pattern-navigator.md
    ├── methods/
    │   └── <category>/*.md
    ├── patterns/
    │   └── *.md
    ├── machine-learning.md
    └── machine-learning/*.md
```

`ict-methods/` is self-contained: the skill and everything it reads live under that one folder, so installing it is just copying that folder.

| Path | What it is |
|---|---|
| `SKILL.md` | the skill itself |
| `references/index.md` | flat name/category/phases/why table for all 56 methods — read once per session instead of re-grepping `methods/` on every check |
| `references/methods/<category>/*.md` | 56 method cards (`field`, `lab`, `library`, `showroom`, `workshop`, `extra`) |
| `references/dot-framework.md` | DOT framework theory (domains, trade-off scales, strategies) |
| `references/research-pattern-navigator.md` | question → pattern lookup table |
| `references/patterns/*.md` | 6 research patterns (Why/How/When/Risks/Examples) |
| `references/machine-learning.md` + `references/machine-learning/*.md` | ML-specific method guidance |

## Install

Clone this repo, then copy (or symlink) the `ict-methods/` folder into your tool's skills directory — not the repo root.

```bash
git clone <this-repo-url>
```

**Claude Code**

- Personal, all projects: `cp -r ict-methods ~/.claude/skills/ict-methods`
- One project only: `cp -r ict-methods <your-project>/.claude/skills/ict-methods`

**Generic Agent Skills convention**

```bash
cp -r ict-methods <your-project>/.agent/skills/ict-methods
```

**Kiro**

```bash
cp -r ict-methods <your-project>/.kiro/skills/ict-methods
```

A symlink instead of `cp -r` works too, and keeps the skill updated on `git pull`:

```bash
ln -s "$(pwd)/ict-methods" <your-tool's-skills-dir>/ict-methods
```

## Usage

```
/ict-methods
```

**Lookup** — ask what a method is, or describe an activity and ask what it's called. The skill matches it in `references/index.md` and returns the full card (why/how/practice/ingredients/phases) — no verdict, just the definition.

**Recommend** — describe a research question or activity instead ("how do I find out what stakeholders actually want?"), with the phase if you know it. The skill checks the pattern navigator for a matching multi-step pattern, ranks candidate methods by phase fit and trade-off scales, and reports a top pick plus alternatives with rationale and prerequisites.

**Validate** — describe your methodology (the method(s) you picked per research phase, and why), or point at a file/paste containing it. The skill looks each method up, checks phase fit against the DOT framework, checks prerequisites and justification, checks multi-method combinations against the known research patterns, and reports a verdict per method with alternatives where relevant.

All three modes check `references/index.md` first and only open individual method files for the shortlisted candidates — so a session with several back-to-back questions doesn't re-scan the whole catalogue every time.

## Attribution

Method cards, the DOT framework, and the research patterns in `references/` are adapted from [ictresearchmethods.nl](https://ictresearchmethods.nl), developed by [HBO-i](https://www.hbo-i.nl/). See that site for citation details and licensing of the original content.
