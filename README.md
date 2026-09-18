# ict-methods

A Claude Code (and compatible) agent skill that checks an HBO-ICT research methodology against the [ictresearchmethods.nl](https://ictresearchmethods.nl) standard (HBO-i's DOT framework, method catalogue, and research patterns) — whether your chosen methods are recognized, fit their research phase, have their prerequisites covered, and combine into a known pattern.

It only runs when you explicitly type `/ict-methods` — it never auto-triggers on keywords in normal conversation.

## Layout

```
ict-methods/
  SKILL.md                 the skill itself
  references/               bundled knowledge base (no external calls needed)
    methods/<category>/*.md   56 method cards (field, lab, library, showroom, workshop, extra)
    dot-framework.md          DOT framework theory (domains, trade-off scales, strategies)
    research-pattern-navigator.md   question → pattern lookup table
    patterns/*.md              6 research patterns (Why/How/When/Risks/Examples)
    machine-learning.md + machine-learning/*.md   ML-specific method guidance
```

`ict-methods/` is self-contained: the skill and everything it reads live under that one folder, so installing it is just copying that folder.

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
ln -s "$(pwd)/ict-methods" ~/.claude/skills/ict-methods
```

## Dependencies

None. `references/` is plain Markdown with YAML frontmatter — no scripts, no build step, no network calls. Any agent that can read files and grep can run this skill.

## Usage

```
/ict-methods
```

Describe your methodology (the method(s) you picked per research phase, and why), or point at a file/paste containing it. The skill looks each method up in `references/methods/`, checks phase fit against the DOT framework, checks prerequisites and justification, checks multi-method combinations against the known research patterns, and reports a verdict per method with alternatives where relevant.

## Attribution

Method cards, the DOT framework, and the research patterns in `references/` are adapted from [ictresearchmethods.nl](https://ictresearchmethods.nl), developed by [HBO-i](https://www.hbo-i.nl/). See that site for citation details and licensing of the original content.
