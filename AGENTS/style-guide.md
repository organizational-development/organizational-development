# Playbook: style guide

How to write prose that matches this repository.

Mechanical rules are in
[../spec/conventions.md](../spec/conventions.md#prose-style). This file is about
voice and judgment.


## The register

House style plus depth. Terse, bullet-driven, heavily linked — but with enough
explanation that a reader can act without following any link.

The tone is a senior practitioner briefing a competent colleague who is short of
time. Not a textbook, not a consultant's deck, not a blog post.

**Say the uncomfortable thing plainly.** This is the register:

> There is no evidence that SWOT improves decision quality, and some reason to >
think it harms it: it produces unranked lists, mixes magnitudes, invites >
consensus platitudes, and encourages internal factors to be labelled strengths >
with no comparison point. Its survival is due to familiarity and low cost.

Hedging to avoid offending a framework's advocates is a defect, not politeness.


## Prefer the concrete

Every abstraction should be followed by something you can picture.

| Instead of | Write |
| --- | --- |
| Improve hand hygiene compliance culture | Move the dispenser |
| Enhance psychological safety | The response to the first person who raises something uncomfortable sets the norm for everyone watching |
| Address resistance to change | People are not resisting; they have no slack |
| Optimize the delivery pipeline | Decompose lead time into its waiting stages and attack the largest; it is almost never the coding |

If a sentence would survive being moved into a different repository about a
different subject, it is too abstract.


## Audience examples

All three, in this order, every time: health care, software, executive.

```markdown
* **Health care**: a nurse or junior doctor questioning a senior clinician's
  drug dose. Structural aids — read-back, graded assertiveness, checklists with
  a designated challenge point — work even where the culture has not yet
  changed.

* **Software**: an engineer saying "I don't understand this design" in review,
  or reporting an outage they caused within minutes rather than hours.

* **Executive**: the hardest room. An executive who says "here's what I got
  wrong last quarter" buys more safety than any program.
```

**The executive example is the hardest and the most valuable.** Write it so the
executive is the *subject* of the intervention, not only its sponsor. The easy
version tells a CEO how to fix their organization; the useful version tells them
which of their own behaviors is the finding.

Test each example: could a reader in that role picture a specific Tuesday? If
not, rewrite.


## Structure of an argument

The pattern most sections follow:

1. **The claim**, stated flatly in one sentence.
2. **The mechanism** — why it is true, not just that it is.
3. **The failure mode** — what goes wrong when people get it wrong, named
   specifically enough to be recognized.
4. **The concrete move** — what to actually do differently.

Example, compressed:

> Removing restraining forces is usually more effective than adding driving >
force, because added driving force raises tension and provokes >
counter-pressure. Push harder and you get compliance plus resentment. The most >
common restraining force is workload with no slack, and it is the least often >
addressed: people are not resisting, they have no capacity.


## Things to avoid

* **Emoji, badges, decorative formatting.** None, anywhere.
* **"It is important to note that".** Delete; state the thing.
* **"Best practice" without qualification.** Ask: best for whom, at what, under
  which conditions? The repository is skeptical of the phrase by design.
* **Invented numbers.** No fabricated effect sizes, percentages, sample counts,
  or study totals. Where a documented finding exists, describe it in general
  terms ("documented productivity drops for weeks to months after electronic
  health record go-live"); where one does not, describe the mechanism.
* **Framework advocacy.** Every model gets its limitations section and its
  honest evidence label, including the ones you like.
* **Undifferentiated lists.** A list of twelve items with no ranking is a
  research note, not a deliverable. Rank, or cut.
* **Passive evasion.** "Mistakes were made" — name who does what.


## Mechanical rules

Full list in [../spec/conventions.md](../spec/conventions.md#prose-style). Most
frequently forgotten:

* **Hard-wrap prose at 80 columns.** Do not wrap tables, code blocks, or URLs.
* **Sentence case headings**, always. `## Examples by audience`, not
  `## Examples By Audience`.
* **Em dash spaced** ` — `; en dash in ranges `1–5`.
* **Two blank lines** before `## `, one before `### `.
* **Bold lead-ins** on defining list items: `* **Autonomy** — ...`.
* **Cross-topic links** are `../<topic>/` with the trailing slash.

Check wrapping before committing:

```sh
awk 'length > 80 && !/^\||^```|^ *\* \[|http/ {print FILENAME": "FNR": "length}' \
  topics/*/index.md | head -20
```

Long table rows and link lines are expected; long prose lines are not.


## Terminology

Consistent usage across the repository:

| Use | Not |
| --- | --- |
| organizational development, OD | org dev, OD&D |
| health care (two words) | healthcare |
| psychological safety | psych safety |
| after action review | post-mortem, when meaning the AAR specifically |
| knowledge worker | resource, headcount |
| people, staff, clinicians, engineers | human capital, FTEs |

The last row is a value statement, not a preference. This repository holds that
people are ends, not merely means to productivity, and the vocabulary reflects
it. See [../topics/od-ethics/](../topics/od-ethics/).
