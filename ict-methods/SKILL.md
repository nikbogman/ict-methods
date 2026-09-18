---
name: ict-methods
description: Checks an HBO-ICT research methodology against the ictresearchmethods.nl standard, or recommends which method(s) fit a research question or activity — validates chosen methods (recognized, phase fit, prerequisites) and/or suggests methods when none are chosen yet.
disable-model-invocation: true
---

# /ict-methods

Works against `references/`, the official HBO-ICT method catalogue mirrored from [ictresearchmethods.nl](https://ictresearchmethods.nl), grounded in the [DOT framework](references/dot-framework.md) (domains, trade-off scales, strategies) and its [research patterns](references/research-pattern-navigator.md). Each file in `references/methods/<category>/<method>.md` is one canonical method with YAML frontmatter (`name`, `why`, `how`, `practice`, `ingredients`, `category`, `phases`, `scales`).

**Categories / DOT strategies** (research setting): `field`, `lab`, `library`, `showroom`, `workshop`, `extra`.
**Phases** (research stage): `problem-definition`, `analysis`, `design`, `realisation`, `evaluation`, plus the cross-cutting `machine-learning`.

## Pick a mode

- The user names method(s) they've picked or are using, per phase → **Validate**.
- The user describes a research question or activity without naming a method → **Recommend**.
- Both at once (e.g. "does X fit, or is there something better?") → run Validate on what's named, then Recommend for the gap.

## Recommend

1. **Get the question or activity**, and if given, the phase and whether it's ML-related (a component that learns from data — this changes step 2). If the phase is missing, infer the closest fit from the question's wording rather than blocking on it; state the inferred phase in the report.

2. **Check for a matching pattern first.** If the question spans more than a single research step (it implies a sequence, e.g. "how do I get from vague stakeholder wishes to a validated solution?"), match it against `references/research-pattern-navigator.md`'s question table. A hit means the recommendation is a pattern, not a single method — read the matching `references/patterns/*.md` file and its How/When/Risks sections.

3. **Rank candidate methods.** Whether or not a pattern matched (a pattern's steps still resolve to individual methods), search `references/methods/**/*.md` (or, if ML-related, `references/machine-learning.md` and the matching `references/machine-learning/<category>-methods.md` first) for methods whose `why`/`practice` address the question's intent. Filter to methods whose `phases` includes the (given or inferred) phase. Rank by fit using the `scales` frontmatter against what the question needs — e.g. a question about validating a hunch needs certainty/data, one about generating options needs overview/inspiration.

4. **Report.** Top pick (or the matched pattern's method sequence) with the `why` it fits, its `ingredients` (what the user needs to have ready), and up to 2 runner-up alternatives with a one-line reason each was ranked lower.

## Validate

1. **Get the methodology.** Use what the user already described in this conversation, or a file/paste they point to. It must name, per research phase: the method(s) chosen and why. If any phase has no method named, ask the user for it before continuing. Note whether the project is ML-related (a component that learns from data) — this changes step 2 — and whether the named methods span more than one strategy/category combined across phases, rather than a single method in isolation — this triggers step 6.

2. **Look up every named method.**
   - If the project is ML-related, first check `references/machine-learning.md` and the matching `references/machine-learning/<category>-methods.md` (e.g. `lab-methods.md`, `field-methods.md`) for how that strategy adapts to ML. In particular, a named "Data analytics" (Lab) method does not fit ML projects — per `references/machine-learning.md` it decomposes into data collection, exploratory data analysis, data preparation, data quality check, ML model training, model validation, and model evaluation. Look up the ML-specific method cards (exploratory data analysis, data quality check, model validation, model evaluation) in place of the generic Data analytics card; the other three are engineering steps, not research methods, and don't get a verdict.
   - Grep `references/methods/**/*.md` frontmatter `name:` for a match (case-insensitive, tolerate near-spellings — e.g. "AB testing" → `methods/lab/a-b-testing.md`). Read the matched file's frontmatter.
   - No match found → verdict `Not recognized`. Name the closest match by string similarity, or say none exists.
   - Match found → carry its `category`, `phases`, `ingredients`, and `scales` into the next step.

3. **Check phase fit.** Compare the phase the user applied the method to against that method's `phases` list, grounded in `references/dot-framework.md`'s vocabulary rather than the phase list alone:
   - Which domain (application, available work, or innovation) the method actually researches, versus what the phase calls for.
   - Where the method sits on the fit/expertise, overview/certainty, and data/inspiration trade-off scales (its `scales` frontmatter), versus what the phase needs — e.g. early phases typically favor overview/inspiration, later phases favor certainty/data.
   - Listed in `phases` and consistent with the domain/scale reasoning → `Valid`.
   - Not listed, or listed but the domain/scale reasoning is off → verdict `Phase mismatch`, naming which phases the catalogue does list it for and why the domain/scale fit doesn't hold.

4. **Check prerequisites.** Compare the method's `ingredients` against what the user's description says they have in place (participants, tools, data, skills, etc.).
   - All covered → note it.
   - Gaps → verdict `Missing prerequisite`, listing the uncovered ingredients.

5. **Check justification.** Compare the user's stated reason for picking the method against the method's own `why`/`practice` fields.
   - Aligned → note it.
   - Thin, absent, or contradicted by `practice` → verdict `Missing justification`.

6. **Check pattern fit.** If the methodology combines methods from more than one strategy across phases (flagged in step 1), look up the combination in `references/research-pattern-navigator.md` and read the matching `references/patterns/*.md` file.
   - Combination matches a listed pattern → name the pattern, and compare the user's sequencing/reasoning against its How/When sections; if it diverges, flag the divergence and surface the pattern's Risks section.
   - Combination doesn't match any known pattern → verdict `Unrecognized strategy combination`, pointing at the nearest pattern(s) by shared strategies for comparison.
   - Only a single method or single strategy named → not applicable, skip.

7. **Suggest alternatives per phase.** For each phase in the methodology, grep `references/methods/**/*.md` for other methods whose `phases` includes that phase (for ML-related phases, prefer the ML-specific method cards surfaced in step 2). From those, surface up to 3 the user didn't pick — favor ones in the same `category` as their intended research setting — when their chosen method scored anything other than a clean `Valid` in steps 3–5.

8. **Report.** One row per method the user named: method → verdict(s) from steps 2–5 → the alternatives from step 7 (if any). Add one line for the pattern check from step 6 (pattern matched with any divergence noted, unrecognized combination, or not applicable). Every named method must have reached step 2 and been given an explicit verdict — don't summarize without one.
