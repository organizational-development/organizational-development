# AGENTS.md

Operational guidance for coding agents working in this repository.

This file tells you how to work here. It does **not** restate the conventions —
those live in [spec/conventions.md](spec/conventions.md), which is the single
source of truth. Read that file before your first edit.

Contents:

* [What this repository is](#what-this-repository-is)
* [Layout](#layout)
* [The five invariants](#the-five-invariants)
* [Before you start](#before-you-start)
* [Validation](#validation)
* [Task playbooks](#task-playbooks)
* [What to be careful about](#what-to-be-careful-about)
* [Commit conventions](#commit-conventions)


## What this repository is

A comprehensive organizational development (OD) guide for knowledge workers in
three settings: health care, software engineering, and senior executive
leadership.

The deliverable is `README.md`: a self-contained guide a reader can act on
without following a single link. Everything under `topics/` is the deeper
reference layer behind it.

**The repository's distinguishing commitment** is honesty about evidence. Most
published OD writing presents every framework as equally sound. This one labels
each model's empirical support and says plainly where it is weak. Five models
out of seventy-two have strong support; twenty are flatly weak. Preserving that
honesty is the highest-priority editorial constraint here. Do not soften a
rating to be diplomatic.


## Layout

```
README.md              The deliverable: comprehensive self-contained guide
AGENTS.md              This file
CLAUDE.md              Pointer to this file
CONTRIBUTING.md        The same ground, for human contributors
AGENTS/                Task playbooks, one per recurring task
bin/audit              Validation; exits non-zero on any violation
.github/workflows/     CI: runs bin/audit on push and pull request
spec/index.md          Plan of record: decisions, findings, tasks
spec/conventions.md    Single source of truth for how the repo is built
spec/ideas.md          Raw research notes, pre-synthesis
topics/index.md        Canonical inventory of all topics
topics/<name>/index.md One directory per model, framework, method, system
topics/<name>/README.md -> index.md
```

Full detail in [spec/conventions.md](spec/conventions.md#repository-layout).


## The five invariants

Break any of these and the repository stops working. `bin/audit` enforces all
five.

1. **Every topic directory has `index.md` plus a `README.md` symlink to it.**
   The symlink is what makes `topics/foo/` render on GitHub. Create with
   `ln -sfn index.md README.md`.

2. **Every model carries an evidence label** with a permitted strength value,
   placed immediately before the `Use when:` line, stating the specific
   methodological objection rather than a generic hedge.

3. **Every diagnostic model has a paired questionnaire**, linked in both
   directions, with a closing analysis section that says how to read the scores.

4. **Cross-topic links use `../<topic>/`** with a trailing slash. Never
   `foo.md`, never `../foo/index.md`.

5. **Agent files stay under 40 KB.** `README.md` is exempt and is intentionally
   large; it is the deliverable.


## Before you start

1. Read [spec/conventions.md](spec/conventions.md). It is the contract.
2. Read [spec/index.md](spec/index.md) for what has been decided and why, what
   is done, and what is deliberately not done.
3. Run `bin/audit` to confirm you are starting from a clean state.
4. Check whether your task has a playbook in [AGENTS/](AGENTS/).

If a convention seems wrong, change `spec/conventions.md` **first**, in its own
commit, with the reasoning recorded in `spec/index.md`. Do not quietly deviate
in one file; that is how a single source of truth stops being one.


## Validation

```sh
bin/audit           # full report
bin/audit --quiet   # failures only; use in CI
```

Nineteen checks: directory structure, single title per topic, evidence labels
and their permitted values, `Use when` and `Do not use when`, questionnaire
pairing in both directions, cross-topic links, absence of legacy links, README
links, README anchors, agent file size, topic index completeness, presence of
the required top-level files, currency of the stated model count, all three
audience examples, absence of orphan topics, 80-column prose wrapping, and three
self-documentation checks: the check list in `spec/conventions.md`, the check
table in `AGENTS/audit.md`, and every "<n> checks" claim in prose.

**Run it before every commit.** If a check disagrees with `spec/conventions.md`,
the check is the bug — fix the script, not the content.


## Task playbooks

| Task | Playbook |
| --- | --- |
| Add a new model, framework, method, or system | [AGENTS/add-a-topic.md](AGENTS/add-a-topic.md) |
| Add or revise a questionnaire | [AGENTS/add-a-questionnaire.md](AGENTS/add-a-questionnaire.md) |
| Assign or change an evidence label | [AGENTS/evidence-labels.md](AGENTS/evidence-labels.md) |
| Write prose that matches the house voice | [AGENTS/style-guide.md](AGENTS/style-guide.md) |
| Audit, fix, or extend the checks | [AGENTS/audit.md](AGENTS/audit.md) |

Each playbook is self-contained and under 40 KB.


## What to be careful about

**Cascading updates.** These files are coupled. When you change one, check the
others:

| If you change | Also update |
| --- | --- |
| A topic's evidence label | Evidence table in `README.md`; the "Evidence at a glance" table in `topics/index.md`; distribution count in `spec/index.md` |
| A topic name or directory | Every `../<name>/` link; `topics/index.md`; `README.md` see-also; `spec/index.md` inventory |
| Add a topic | `topics/index.md`; `README.md` see-also and probably a body section; `spec/index.md` inventory |
| A README heading | Its anchor in the contents list, and any `(#anchor)` referencing it |
| A convention | `spec/conventions.md` first, then `bin/audit`, then the affected files |
| A `bin/audit` check | The list in `spec/conventions.md`; the table *and* fix entries in `AGENTS/audit.md`; the counts in this file and `CONTRIBUTING.md`. Checks 17–19 fail until all four agree |
| A `README.md` or topic heading | Anchors here, and the published site, which turns headings into URLs — see [spec/index.md](spec/index.md#downstream-the-website) |

**Do not.**

* Do not add a topic without an evidence label. There is no "unrated" state.
* Do not present a weak model as though it were supported, or add hedging
  language that obscures a rating.
* Do not invent statistics, effect sizes, or study counts. Where a documented
  finding exists, describe it in general terms; where one does not, describe the
  mechanism instead.
* Do not use `README.md` inside `topics/` as a real file. It is always a
  symlink.
* Do not add emoji, badges, or decorative formatting.
* Do not commit unless the user asked. Run `bin/audit` and report instead.

**Do.**

* Prefer editing an existing topic to creating a near-duplicate one.
* Keep all three audience examples — health care, software, executive — present
  and specific.
* Say the uncomfortable thing plainly. That is the register of this repository.


## Commit conventions

* Present tense, imperative: "Add Westrum questionnaire", not "Added".
* One logical change per commit. Convention changes get their own commit.
* Run `bin/audit` first. Do not commit a failing tree.
* Only commit when the user asks.
