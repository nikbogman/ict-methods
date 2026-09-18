---
name: ict-methods
description: Validates a research methodology against the HBO-ICT research methods standard (ictresearchmethods.nl) — checks that chosen methods are recognized, fit their research phase, and have their prerequisites covered.
disable-model-invocation: true
---

# /ict-methods

Checks a research methodology against `data/`, the official HBO-ICT method catalogue mirrored from [ictresearchmethods.nl](https://ictresearchmethods.nl). Each file in `data/<category>/<method>.md` is one canonical method with YAML frontmatter (`name`, `why`, `how`, `practice`, `ingredients`, `category`, `phases`, `scales`).

**Categories** (research setting): `field`, `lab`, `library`, `showroom`, `workshop`, `extra`.
**Phases** (research stage): `problem-definition`, `analysis`, `design`, `realisation`, `evaluation`, plus the cross-cutting `machine-learning`.

## Steps

1. **Get the methodology.** Use what the user already described in this conversation, or a file/paste they point to. It must name, per research phase: the method(s) chosen and why. If any phase has no method named, ask the user for it before continuing.

2. **Look up every named method in `data/`.** Grep `data/**/*.md` frontmatter `name:` for a match (case-insensitive, tolerate near-spellings — e.g. "AB testing" → `lab/a-b-testing.md`). Read the matched file's frontmatter.
   - No match found → verdict `Not recognized`. Name the closest match by string similarity, or say none exists.
   - Match found → carry its `category`, `phases`, and `ingredients` into the next step.

3. **Check phase fit.** Compare the phase the user applied the method to against that method's `phases` list.
   - Listed → `Valid`.
   - Not listed → verdict `Phase mismatch`, and name which phases the catalogue does list it for.

4. **Check prerequisites.** Compare the method's `ingredients` against what the user's description says they have in place (participants, tools, data, skills, etc.).
   - All covered → note it.
   - Gaps → verdict `Missing prerequisite`, listing the uncovered ingredients.

5. **Check justification.** Compare the user's stated reason for picking the method against the method's own `why`/`practice` fields.
   - Aligned → note it.
   - Thin, absent, or contradicted by `practice` → verdict `Missing justification`.

6. **Suggest alternatives per phase.** For each phase in the methodology, grep `data/**/*.md` for other methods whose `phases` includes that phase. From those, surface up to 3 the user didn't pick — favor ones in the same `category` as their intended research setting — when their chosen method scored anything other than a clean `Valid` in steps 3–5.

7. **Report.** One row per method the user named: method → verdict(s) from steps 2–5 → the alternatives from step 6 (if any). Every named method must have reached step 2 and been given an explicit verdict — don't summarize without one.
