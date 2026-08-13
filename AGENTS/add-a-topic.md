# Playbook: add a topic

Adding a new model, framework, method, or system.

Conventions are defined in [../spec/conventions.md](../spec/conventions.md).
This playbook is the procedure; that file is the contract.


## 1. Decide whether it belongs

Before writing anything, answer these. If any answer is no, do not add it.

* **Is it distinct?** Search `topics/` for near-duplicates. Many OD models are
  restatements of each other. `grep -ril "<keyword>" topics/` is the first move.
  Prefer a section inside an existing topic to a near-duplicate directory.
* **Can you state its evidence honestly?** If you cannot say what supports it
  and what does not, you do not know it well enough yet. There is no unrated
  state.
* **Can you name when *not* to use it?** If you cannot, you are writing
  advocacy, not reference.
* **Does it serve at least one of the three audiences** — health care, software,
  senior executive — concretely?
* **Which family does it belong to?** Foundations and process, diagnostic,
  change, culture, team and individual, facilitation, or measurement.


## 2. Create the directory

```sh
name=my-new-topic
mkdir -p "topics/$name"
cd "topics/$name"
$EDITOR index.md
ln -sfn index.md README.md
cd ../..
```

The symlink is not optional. Without it, `topics/$name/` does not render on
GitHub.


## 3. Write index.md

Required section order:

```markdown
# Title in sentence case

Definition paragraph: what it is, who created it, when. Two to five sentences.
No bullets before the reader knows what they are reading.

**Evidence: <Strength>.** What is supported, what is not, and the specific
methodological objection. Name what survives the criticism. Link to a
better-evidenced alternative where one exists.

Use when: the situations where this is the right tool.

Do not use when: the honest counterpart.


## <The model's own structure>

Its elements, stages, levels, or dimensions.


## Examples by audience

* **Health care**: specific enough to picture.

* **Software**: specific enough to picture.

* **Executive**: address the executive as the subject of the intervention, not
  only as its sponsor.


## Limitations

Practical constraints, costs, and misuse risks. Distinct from the evidence
label, which covers empirical support.


## Questionnaire

Required only for diagnostic models. See
[add-a-questionnaire.md](add-a-questionnaire.md).


## See also

* [sibling-topic](../sibling-topic/)
* Author, *Book Title*.
* <https://example.org>
```

Details on each: evidence labels in [evidence-labels.md](evidence-labels.md),
prose and audience examples in [style-guide.md](style-guide.md).


## 4. Wire it in

A new topic is not done until every one of these is true.

* [ ] `topics/index.md` lists it, in the right family, with its evidence label
      in brackets and a one-line description.
* [ ] `README.md` links to it in the *See also* section, under the right family
      heading.
* [ ] `README.md` covers the material in the body if it is substantial enough to
      belong in the guide — or `spec/index.md` records the decision not to.
* [ ] Related topics link **to** it. A topic nothing links to will not be found.
      Add `See also` entries in at least two siblings.
* [ ] `spec/index.md` inventory lists it.
* [ ] If it is a diagnostic model, the paired questionnaire exists.
* [ ] `bin/audit` passes.


## 5. Check the evidence tables

If the new topic is a model, three tables now disagree with reality:

* the evidence summary table in `README.md`, *Evidence-based practice* section;
* the *Evidence at a glance* table in `topics/index.md`;
* the distribution count in `spec/index.md`, under *Decisions*.

Update all three. Recount rather than incrementing from memory:

```sh
find topics -name index.md -not -path '*-questionnaire/*' \
  -exec grep -h -m1 -o '^\*\*Evidence: [^.]*\.' {} + |
  sed 's/\*\*Evidence: //; s/\.$//' | sort | uniq -c | sort -rn
```

Questionnaires are excluded because each inherits its model's rating, so
counting them would inflate every bucket and disagree with the documented
distribution, which is model-only.


## 6. Validate

```sh
bin/audit
```

Fix anything it reports. Do not adjust the script to make a real violation pass;
the script is only the bug when it disagrees with `spec/conventions.md`.


## Worked example

Adding `psychological-safety` would have run:

1. Distinct? Yes — nothing else covers interpersonal risk-taking.
2. Evidence? Strong; large literature, meta-analytic support; caveats are
   self-report measurement and dependence on task interdependence.
3. Not-use case? As a synonym for comfort, which is the standard misreading.
4. Audiences? Nurse challenging a dose; engineer admitting confusion in review;
   executive admitting a failed bet.
5. Family? Team and individual models.
6. Wire in: listed in `topics/index.md`; body section in `README.md` Part 6;
   linked from `westrum-organizational-culture-typology`, `just-culture`,
   `google-project-aristotle`, `satir-change-model`, and others.


## Common mistakes

* **Creating a topic for a variant.** ERG theory lives inside
  `maslow-hierarchy-of-needs`, not beside it. Variants are sections.
* **Writing the definition as a bullet list.** The reader needs a sentence
  first.
* **Omitting `Do not use when`.** It is required, and it is the part readers
  trust the file for.
* **Generic audience examples.** "Improves communication" is not an example.
* **Forgetting the symlink.** Then the topic renders as a directory listing.
* **Leaving the topic unlinked.** An orphan topic is invisible.
