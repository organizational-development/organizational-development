# Contributing

Contributions are welcome: new topics, corrections, better examples, and
especially disagreement with an evidence label.

Coding agents should read [AGENTS.md](AGENTS.md) instead; it covers the same
ground in the form agents need.


## The short version

1. Read [spec/conventions.md](spec/conventions.md). It is the single source of
   truth for how this repository is built.
2. Make your change.
3. Run `bin/audit`. It must exit zero.
4. Open a pull request describing what changed and why.


## What this repository is trying to be

A practitioner's guide to organizational development that is **honest about
evidence**. Most published OD writing presents every framework as equally sound.
This one labels each model's empirical support and says plainly where it is
weak: across 72 models, 5 are `Strong` and 20 are flatly `Weak`.

That honesty is the point, and it is the thing most likely to be eroded by
well-meaning contributions. Please do not soften a rating to be diplomatic
toward a framework's advocates. The audience is a practitioner deciding whether
to bet a year of organizational effort on a model.


## Especially welcome

**Disagreement with an evidence label.** Every label states its reasoning
precisely so that it can be argued with. If a rating is wrong — because research
has appeared, or because the reasoning is faulty — that is a defect worth
reporting. Open an issue with the specific objection and, where possible, a
source.

**Better audience examples.** Every substantial topic carries an example for
health care, software, and senior executives. Generic examples are a known
weakness; concrete ones drawn from real practice are the fastest way to improve
the guide. "Improves communication" is not an example; "the workstation is two
corridors away and the shift has no slack" is.

**Missing failure modes.** [Part 10](README.md#part-10-anti-patterns) collects
recurring anti-patterns with their tells. If you have watched one that is not
listed, it belongs there.

**Corrections of fact.** Attribution, dates, what a model actually says.


## Adding a topic

Full procedure in [AGENTS/add-a-topic.md](AGENTS/add-a-topic.md). In brief:

```sh
name=my-new-topic
mkdir -p "topics/$name"
cd "topics/$name"
$EDITOR index.md
ln -sfn index.md README.md    # required; without it the directory does not render
cd ../..
bin/audit
```

Required sections, in order: title, definition paragraph, evidence label,
`Use when:`, `Do not use when:`, the model's content, examples by audience,
limitations, and see-also. Diagnostic models also need a paired questionnaire.

Before writing, check for a near-duplicate:

```sh
grep -ril "<keyword>" topics/
```

Many OD models are restatements of each other. Prefer a section inside an
existing topic to a near-duplicate directory.


## Style

Details in [AGENTS/style-guide.md](AGENTS/style-guide.md). The essentials:

* Hard-wrap prose at 80 columns. Do not wrap tables, code blocks, or URLs.
* Sentence case headings.
* Cross-topic links are `../<topic>/` with a trailing slash — never `foo.md`,
  never `../foo/index.md`.
* No emoji, badges, or decorative formatting.
* Prefer the concrete. If a sentence would survive being moved into a repository
  about a different subject, it is too abstract.
* Do not invent statistics, effect sizes, or study counts. Where a documented
  finding exists, describe it in general terms; where one does not, describe the
  mechanism instead.


## Validation

```sh
bin/audit           # full report, section by section
bin/audit --quiet   # failures only
```

Nineteen checks: directory structure and symlinks, single title per topic,
evidence labels and their permitted values, `Use when` and `Do not use when`,
questionnaire pairing in both directions, cross-topic links, absence of legacy
links, README links, README anchors, agent file size, topic index completeness,
presence of the required top-level files, currency of the stated model count,
all three audience examples, absence of orphan topics, 80-column prose wrapping,
and three self-documentation checks that keep the documented check list, the
`AGENTS/audit.md` table, and every "<n> checks" claim in step with the script.

The same script runs in CI on every pull request.

If a check disagrees with [spec/conventions.md](spec/conventions.md), **the
check is the bug** — fix the script, not the content, and say so in the pull
request.


## Cascading updates

These files are coupled. When you change one, check the others.

| If you change | Also update |
| --- | --- |
| An evidence label | The table in `README.md`; *Evidence at a glance* in `topics/index.md`; the distribution count in `spec/index.md` |
| A topic name | Every `../<name>/` link; `topics/index.md`; `README.md` see-also; `spec/index.md` |
| Add a topic | `topics/index.md`; `README.md`; `spec/index.md`; links from at least two sibling topics |
| A README heading | Its entry in the contents list, and any `(#anchor)` referencing it |
| A convention | `spec/conventions.md` first, then `bin/audit`, then the affected files |

To recount evidence labels rather than adjusting by hand:

```sh
find topics -name index.md -not -path '*-questionnaire/*' \
  -exec grep -h -m1 -o '^\*\*Evidence: [^.]*\.' {} + |
  sed 's/\*\*Evidence: //; s/\.$//' | sort | uniq -c | sort -rn
```

Questionnaires are excluded because each inherits its model's rating, so
counting them would inflate every bucket and disagree with the documented
distribution, which is model-only.


## Pull requests

* One logical change per pull request.
* Present tense, imperative commit messages: "Add Westrum questionnaire".
* Say what changed and why. For an evidence label change, say what evidence
  moved it.
* Confirm `bin/audit` passes.


## Conduct

Be straightforward and assume good faith. Disagreement about evidence is the
intended mode of this repository, not a conflict to be avoided — but argue with
the claim, not the person making it.
