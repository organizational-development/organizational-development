# Playbook: evidence labels

Assigning or changing a model's evidence label.

This is the repository's most important editorial mechanism. Most published OD
writing presents every framework as equally sound; this one does not. Get this
right and the rest matters less.

Definitions in [../spec/conventions.md](../spec/conventions.md#evidence-labels).


## The format

Placed immediately before the `Use when:` line, wrapped at 80 columns:

```markdown
**Evidence: Strong.** The best-evidenced construct in this collection. A large
literature spanning three decades links it to learning behavior, error
reporting, information sharing, innovation, and performance, with meta-analytic
support and effects that hold across sectors including health care and software.
Two honest caveats: most measurement is self-report, and the relationship with
performance is strongest where work is interdependent and uncertain, which is
precisely this guide's audience.
```

Three parts, in order:

1. **The strength value.** One of the permitted set below.
2. **What supports it, or fails to.** The specific evidence, named.
3. **The honest caveats**, and what survives them.


## Permitted strength values

| Value | Bar for using it |
| --- | --- |
| `Strong` | Meta-analytic or large replicated experimental support |
| `Good` | Substantial empirical support, some methodological limits |
| `Moderate` | The underlying principle has support; the model itself untested |
| `Mixed` | Genuinely contested, or components differ sharply |
| `Contested` | Influential and seriously criticized on method |
| `Weak` | Practitioner-derived, little or no independent validation |
| `Very weak` | Contradicted, or transferred from an unrelated domain |
| `Not an empirical model` | A taxonomy, checklist, or process convention |
| `Not a model` | A method or evaluation practice rather than a claim |
| `Normative, not empirical` | Value commitments, to be argued not measured |

`bin/audit` rejects anything outside this set. To add a value, change
`spec/conventions.md` and the `EVIDENCE_RE` in `bin/audit` together.


## Split labels

Use one when a single value would mislead.
Form: `<value> as a <X>, <value> as a <Y>`.

Established examples:

* `Weak as a model, well documented as a phenomenon` — Satir. The five stages
  are unvalidated; the performance dip they describe is repeatedly documented.
* `Good in aviation, moderate to good in health care` — crew resource
  management. Evidence strength genuinely differs by sector.
* `Weak as research, strong as practitioner consensus` — process consultation,
  entry and contracting. No trials, near-universal professional endorsement.
* `Moderate as a principle, weak as an instrument` — SPACE. The multi-metric
  claim is supported; there is no validated instrument.
* `Weak as a whole, good in its components` — team topologies. The taxonomy is
  untested; Conway's law and cognitive load are not.
* `Weak empirically, high conceptual utility` — Cynefin. Not validatable in its
  current form, and it names a real and costly mistake.

Split labels are encouraged. A blanket rating that hides a real distinction is
worse than a longer honest one.


## How to decide a rating

Work through these in order.

1. **What is the primary source?** A practitioner book, a consulting firm's
   observation, or peer-reviewed research? Practitioner-derived with no
   independent test is `Weak` by default.
2. **Has anyone tested the model as a whole**, or only its components? Component
   support with an untested whole is `Moderate` at best.
3. **How large and how replicated?** A single study, however good, is not
   `Strong`. Meta-analysis or repeated independent replication is the bar.
4. **What is the sample and the era?** Single company, single country, single
   decade, unrepresentative respondents — all pull the rating down and all
   should be named explicitly.
5. **Is measurement self-report?** Very common in this field. Name it; it does
   not by itself disqualify.
6. **Is the effect correlational or causal?** Say which. `Good` findings in this
   repository are frequently correlational, and the label says so.
7. **Has it been contradicted?** Contradicted plus still popular is `Very weak`,
   not `Weak`.


## Rules

* **Be specific.** "Single company, single era, mostly male professional
  respondents, dimensions derived by factor analysis on limited items" beats
  "has been criticized". The specificity is what makes the label trustworthy.
* **Name what survives.** A weak model is often good shared vocabulary. Say so,
  and say what it must not be used for — usually predicting outcomes.
* **Link to the better alternative.** If a stronger model covers the same
  ground, link to it in the label. Kübler-Ross links to Bridges and Satir.
* **Name active harms, not just weakness.** Kübler-Ross's label says that
  labelling a colleague "in denial" converts a substantive objection into a
  psychological symptom. That is more useful than the rating alone.
* **Do not invent numbers.** No fabricated effect sizes, sample counts, or study
  totals. Describe in general terms, or describe the mechanism.
* **Do not soften to be diplomatic.** Advocates of a framework are not the
  audience. Practitioners deciding whether to bet a year on it are.


## Changing an existing label

A label change is a content change with three downstream effects:

1. The evidence summary table in `README.md`, *Evidence-based practice* section.
2. The *Evidence at a glance* table in `topics/index.md`.
3. The distribution count in `spec/index.md`, under *Decisions*.

Recount rather than adjusting by hand:

```sh
find topics -name index.md -not -path '*-questionnaire/*' \
  -exec grep -h -m1 -o '^\*\*Evidence: [^.]*\.' {} + |
  sed 's/\*\*Evidence: //; s/\.$//' | sort | uniq -c | sort -rn
```

Questionnaires are excluded because each inherits its model's rating, so
counting them would inflate every bucket and disagree with the documented
distribution, which is model-only.

Also check whether the guide's prose about that model needs revising. If
`README.md` calls something well-supported and the label now says `Weak`, the
prose is wrong.


## The current distribution

Across 72 labelled model files: 5 `Strong`, 6 `Good`, 9 `Moderate`, 5 `Mixed`, 1
`Contested`, 20 `Weak`, 2 `Very weak`, 17 split labels, 7 non-empirical.

This distribution is unflattering to the field and it is accurate. If a change
you are making pushes the distribution upward, check that the evidence justifies
it rather than that the writing has become more generous.
