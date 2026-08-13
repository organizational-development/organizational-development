# Conventions

This file is the **single source of truth** for how this repository is built.
Every other file defers to it. If a convention is stated here and contradicted
elsewhere, this file wins and the other file is a bug.

Audience: contributors and coding agents. Operational entry point for agents is
[AGENTS.md](../AGENTS.md), which links here rather than restating any of it.

Contents:

* [Repository layout](#repository-layout)
* [Naming](#naming)
* [Topic file structure](#topic-file-structure)
* [Evidence labels](#evidence-labels)
* [Questionnaire pairing](#questionnaire-pairing)
* [Link style](#link-style)
* [Prose style](#prose-style)
* [Audience examples](#audience-examples)
* [README structure](#readme-structure)
* [Validation](#validation)
* [Definition of done](#definition-of-done)


## Repository layout

```
.
├── README.md              The deliverable: comprehensive self-contained guide
├── AGENTS.md              Operational entry point for coding agents
├── CLAUDE.md              Pointer to AGENTS.md; holds no content of its own
├── CONTRIBUTING.md        The same ground, for human contributors
├── CITATION.cff           Citation metadata
├── LICENSE.md             License
├── .github/
│   └── workflows/
│       └── audit.yml      CI: runs bin/audit on push and pull request
├── AGENTS/                Task playbooks for agents, one per recurring task
│   ├── add-a-topic.md
│   ├── add-a-questionnaire.md
│   ├── evidence-labels.md
│   ├── style-guide.md
│   └── audit.md
├── bin/
│   └── audit              Validation script; exits non-zero on any violation
├── spec/                  Specification: what we are building and why
│   ├── index.md           Plan of record: decisions, findings, inventory, tasks
│   ├── conventions.md     This file: the single source of truth
│   └── ideas.md           Raw research notes, pre-synthesis
└── topics/                One directory per model, framework, method, system
    ├── index.md           Index of all topics
    ├── README.md -> index.md
    └── <topic-name>/
        ├── index.md       The topic content
        └── README.md -> index.md
```

**Why the symlink.** Each topic directory contains `index.md` as the real file
and `README.md` as a symlink to it. GitHub renders `README.md` when a visitor
opens a directory, so a link to `topics/psychological-safety/` displays the
content. `index.md` is the canonical name; static site generators and local
tooling expect it.

Create it with:

```sh
ln -sfn index.md README.md
```

**Every directory under `topics/` must contain both**, without exception.


## Naming

* **kebab-case** for all directory and file names: `psychological-safety`,
  `mckinsey-7s-framework`.
* **No abbreviations** unless the abbreviation is the common name of the thing:
  `dora-metrics`, `space-framework`, `swot-analysis` are correct.
* **Named models carry the originator's name** in the form the literature uses:
  `burke-litwin-causal-model`, `nadler-tushman-congruence-model`,
  `thomas-kilmann-conflict-modes`.
* **Questionnaires** are the model name plus `-questionnaire`:
  `weisbord-six-box-model-questionnaire`.
* **ASCII only in filenames.** The topic is `world-cafe`, not `world-café`.
  Accented characters are fine in prose and headings.
* **One topic per directory.** If a file needs two `#` level-one headings, it is
  two topics.


## Topic file structure

Every `topics/<name>/index.md` follows this order. Sections marked *required*
must be present; the rest are included when they have something to say.

1. **`# Title`** — *required*. Sentence case, matching the directory name in
   meaning but not necessarily in punctuation. One per file.

2. **Definition paragraph** — *required*. What the thing is, who created it, and
   when, in two to five sentences. No bullet list before the reader knows what
   they are reading.

3. **`**Evidence: <strength>.**` block** — *required for every model, framework,
   method, and system*. See [evidence labels](#evidence-labels). Placed
   immediately before the "Use when" line.

4. **`Use when:`** — *required*. One sentence or a short list. Plain paragraph,
   not a heading.

5. **`Do not use when:`** — *required*. The honest counterpart. If you cannot
   name a situation where the model is the wrong choice, you do not understand
   it well enough to write about it yet.

6. **Content sections** — `## `-level. The model's actual structure: its
   elements, stages, levels, or dimensions.

7. **`## Examples by audience`** — *required for substantial topics*. See
   [audience examples](#audience-examples).

8. **`## Limitations`** — *required*. Distinct from the evidence label: the
   evidence label covers empirical support, limitations cover practical
   constraints, costs, and misuse risks.

9. **`## Questionnaire`** — *required for diagnostic models*. See
   [questionnaire pairing](#questionnaire-pairing).

10. **`## See also`** — *required*. Sibling topics first, then external sources
    and books.

Questionnaire files use a different structure: title, purpose paragraph, a link
back to the model, the evidence label, numbered `## Step N:` sections, and a
closing `## Analysis` or `## Step N: Analysis` section that tells the reader how
to interpret the scores.


## Evidence labels

The repository's clearest point of difference from typical OD content is that it
says which models are supported and which are not. Most published OD writing
presents every framework as equally sound. This one does not.

**Format**, placed immediately before the `Use when:` line:

```markdown
**Evidence: Strong.** The best-evidenced construct in this collection. A large
literature spanning three decades links it to learning behavior, error
reporting, information sharing, innovation, and performance, with meta-analytic
support and effects that hold across sectors including health care and software.
Two honest caveats: most measurement is self-report, and the relationship with
performance is strongest where work is interdependent and uncertain.
```

**Permitted strength values**, strongest to weakest:

| Value | Meaning |
| --- | --- |
| `Strong` | Meta-analytic or large replicated experimental support |
| `Good` | Substantial empirical support, some methodological limits |
| `Moderate` | Real support for the underlying principle, model itself untested |
| `Mixed` | Genuinely contested, or components differ sharply in support |
| `Contested` | Influential and seriously criticized on method |
| `Weak` | Practitioner-derived, little or no independent validation |
| `Very weak` | Contradicted, or transferred from an unrelated domain |
| `Not an empirical model` | A taxonomy, checklist, or process convention |
| `Normative, not empirical` | Value commitments, to be argued not measured |

**Split labels are permitted and encouraged** where a single value would
mislead. Use the form `<value> as a <X>, <value> as a <Y>`:

* `Weak as a model, well documented as a phenomenon`
* `Good in aviation, moderate to good in health care`
* `Weak as research, strong as practitioner consensus`
* `Moderate as a principle, weak as an instrument`

**Rules:**

* State the **specific** methodological objection, not a generic hedge. "Single
  company, single era, mostly male professional sample, factor analysis on
  limited items" beats "has been criticized".
* Name what **survives** the criticism. A weak model is often still a useful
  vocabulary; say so, and say what it must not be used for.
* Where a better-evidenced alternative exists, **link to it**.
* Do not soften a rating to be diplomatic. The distribution across this
  repository is unflattering to the field, and that is the accurate picture.
* When a label changes, update the summary table in `README.md` in the
  *Evidence-based practice* section, and the distribution count in
  `spec/index.md`.


## Questionnaire pairing

**Every diagnostic model has a paired questionnaire.** The model file explains;
the questionnaire operationalizes. This pairing is the repository's most
distinctive asset, because most public OD writing stops at explanation.

Two culture and team models also have one, because they carry published,
validated instruments and are the best-evidenced constructs in the collection:
`psychological-safety` and `westrum-organizational-culture-typology`. Other
culture and team models do not, and should not acquire one unless they have a
real instrument behind them. A questionnaire implies a precision that most of
these models do not have.

* The questionnaire lives at `topics/<model>-questionnaire/index.md`.
* The model file carries a `## Questionnaire` section linking to it.
* The questionnaire links back to the model in its opening.
* Default form: numbered `## Step N:` sections, items with a `Question:` line
  and a `Rating (1–5): [ ]` line, and a closing analysis step.

**Depart from the default form when it would be dishonest**, and say so in the
file. Established departures:

* Inverted scale where a high score is a warning, not a good result
  (`leavitt-diamond-model-questionnaire`).
* Two-part structure where appraising the model matters as much as scoring
  against it (`maturity-models-questionnaire`).
* Worksheet with evidence and confidence columns where the value is in a pairing
  or plotting step rather than a score (`swot-analysis-questionnaire`,
  `pestle-analysis-questionnaire`).
* Domain placement rather than scale scoring
  (`cynefin-framework-questionnaire`).
* A practitioner ethics gate that must be completed before the participant
  survey, with hard stops rather than trade-offs
  (`organizational-network-analysis-questionnaire`).

The closing analysis section is not optional. A questionnaire that produces
numbers and does not say how to read them is worse than no questionnaire,
because it invites confident misreading.


## Link style

* **Cross-topic links use a relative directory path with a trailing slash**:
  `[psychological-safety](../psychological-safety/)`. The trailing slash
  resolves to that directory's `README.md` symlink on GitHub.
* **From `README.md` to a topic**:
  `[topics/psychological-safety](topics/psychological-safety/)`.
* **Never link to `index.md` directly** across topics. Link to the directory.
* **Never use bare `.md` sibling links** such as `[foo](foo.md)`; that was the
  pre-`topics/` layout and no longer resolves.
* **External links** use angle brackets when the URL is the link text
  (`<https://example.org>`) and markdown links otherwise.
* **Related repositories** are linked at full URL under
  `https://github.com/joelparkerhenderson/<repo>`.


## Prose style

House style, plus enough depth that a reader can act without following links.

* **Hard-wrap prose at 80 columns.** Do not wrap tables, code blocks, or long
  URLs.
* **Bold lead-ins** on list items that define a term: `* **Autonomy** — ...`.
* **Em dashes** for parenthetical breaks, spaced as ` — `.
* **En dashes** in numeric ranges: `1–5`, `6–18 months`.
* **Sentence case** for all headings.
* **Two blank lines** before a `## ` heading, one before a `### `.
* **No emoji.** No decorative badges.
* **Say the uncomfortable thing plainly.** "There is no evidence that SWOT
  improves decision quality, and some reason to think it harms it" is the
  register. Hedging to avoid offending a framework's advocates is a defect.
* **Prefer the concrete.** "Move the dispenser" beats "improve compliance
  culture".
* **Second person for instructions, third person for description.**


## Audience examples

The guide targets three audiences, and every substantial topic carries an
example for each, interleaved rather than segregated into separate chapters.

* **Health care** — doctors, nurses, allied health, administrators.
* **Software** — designers, developers, testers, architects, engineering
  managers.
* **Senior executives** — CEO, CIO, CTO, CHRO, and public-sector equivalents.

Format inside `## Examples by audience`:

```markdown
* **Health care**: a nurse escalating a medication concern to a senior
  physician. Structural aids — read-back, graded assertiveness — work even
  where the culture has not yet changed.

* **Software**: an engineer saying "I don't understand this design" in review.

* **Executive**: the hardest room. An executive who says "here's what I got
  wrong last quarter" buys more safety than any program.
```

**Rules:**

* All three, in this order, every time.
* Each example must be **specific enough to picture**. "Improves communication"
  is not an example.
* The executive example should address the executive as the **subject** of the
  intervention, not only as its sponsor. This is the hardest one to write and
  the most valuable.
* Do not invent statistics. Where a documented finding exists, cite it in
  general terms ("documented productivity drops for weeks to months after
  electronic health record go-live"); where one does not, describe the mechanism
  instead.


## README structure

`README.md` is the deliverable and is deliberately large and self-contained. A
reader must be able to act without following a single link.

* Eleven numbered parts plus introduction, glossary, and see-also. The order is
  recorded in [index.md](index.md) under *Deliverable outline*.
* Every heading referenced in the contents list must exist, and every
  `(#anchor)` must resolve. `bin/audit` checks this.
* The evidence summary table in the *Evidence-based practice* section must agree
  with the labels in the topic files.
* Size is not constrained. The 40 KB budget applies to agent files, not to the
  guide.


## Validation

Run `bin/audit` before committing. It checks:

1. Topic directory structure.
2. Exactly one level-one heading per topic.
3. Evidence labels present and using a permitted strength value.
4. Model topics declare Use when and Do not use when.
5. Diagnostic models paired with questionnaires, both directions.
6. Cross-topic links resolve.
7. No legacy bare .md sibling links.
8. README links resolve.
9. README anchors resolve to headings.
10. Agent files under 40 KB.
11. topics/index.md lists every topic.
12. Required top-level files present.
13. Stated model count matches reality.
14. Model topics carry all three audience examples.
15. Every topic is linked from at least one sibling.
16. Prose wrapped at 80 columns.
17. Validation list in conventions.md matches these checks.

The script exits non-zero on any violation and prints the offending file.

**This list must stay 1:1 with the `section` calls in `bin/audit`.** Check 17
enforces that: adding a check without documenting it here fails the audit, and
so does documenting one that does not exist.

## Definition of done

A change is done when all of the following hold.

* [ ] `bin/audit` exits zero.
* [ ] New topics have all required sections in the required order.
* [ ] New models carry an evidence label with a specific, sourced justification.
* [ ] New diagnostic models have a paired questionnaire with an analysis step.
* [ ] All three audience examples are present and specific.
* [ ] `README.md` covers the new material, or a deliberate decision not to is
      recorded in [index.md](index.md).
* [ ] `topics/index.md` lists the new topic in the right family.
* [ ] [index.md](index.md) inventory and tasks are updated.
* [ ] Prose is wrapped at 80 columns.
