# Organizational Development — specification index

This directory is the working specification for the repository. The deliverable
is the top-level `README.md`: a comprehensive, self-contained organizational
development (OD) guide for knowledge workers.

Contents:

* [Original prompt](#original-prompt)
* [Decisions](#decisions)
* [Findings](#findings)
* [Deliverable outline](#deliverable-outline)
* [Spec file inventory](#spec-file-inventory)
* [Tasks](#tasks)
* [Suggested improvements](#suggested-improvements)
* [Open questions](#open-questions)


## Original prompt

- Research spec/*.md specification-driven-development.
- Research organizational development.
  - Ask me questions as you think.
  - Suggest improvements as you think.
  - Update this file spec/index.md with your findings, plans, tasks, etc.
- Write a comprehensive organizational development guide.
- Target audience is knowledge workers such as:
  - health care professionals e.g. doctors, nurses, administration
  - software engineers e.g. designers, developers, testers
  - senior executives e.g. CEO, CIO, CTO, CHRO.
- Output file is markdown and name is README.md.

Follow-up instructions:

- Add more files to spec/, one file per model, or framework, or system, etc.
- Cover the "Process, measurement & ethics" family in full.


## Decisions

Decisions confirmed with the repository owner:

* **Structure**: `README.md` is a self-contained comprehensive guide. A reader
  should be able to act without following any link. `spec/` holds one reference
  file per model, framework, method, or system, plus these working notes.

* **Audience handling**: interleave concrete examples from all three audiences
  throughout the body, rather than segregating audiences into separate chapters.
  Every substantial model gets health care, software, and executive examples.

* **Coverage**: all four framework families.
  1. Diagnostic models.
  2. Change models.
  3. Culture, team, and human models.
  4. Process, measurement, and ethics.

* **Style**: house style plus depth. Terse bullet-driven sections, bold lead-ins,
  heavy linking, `See ...` references — but with enough explanation, tables, and
  worked examples that the guide teaches rather than merely indexes.

* **Conventions**: kebab-case filenames; one topic per file; each spec file
  carries a short definition, an origin, the model content, a
  "When to use / when not to use" pair, limitations, and sources.

* **Evidence labelling**: every model, framework, method, and system file
  carries a `**Evidence: <strength>.**` block placed immediately before the
  "Use when" line. It states plainly what is supported, what is not, and what
  the specific methodological objections are. Strength values in use, from
  strongest to weakest: `Strong`, `Good`, `Moderate`, `Mixed`, `Contested`,
  `Weak`, `Very weak`, plus split labels of the form
  "Weak as a model, moderate in components" where a blanket rating would
  mislead, and `Not an empirical model` for taxonomies, checklists, methods,
  and normative material. The current distribution across 68 labelled files is
  4 Strong, 5 Good, 8 Moderate, 5 Mixed, 1 Contested, 20 Weak, 2 Very weak,
  plus 16 split labels and 7 non-empirical.

* **Questionnaire pairing**: every diagnostic model has a paired
  `<model>-questionnaire.md` operational instrument, cross-linked from a
  `## Questionnaire` section in the model file. Questionnaires use a 1–5 rating
  scale, numbered steps, and a closing analysis step that says how to read the
  scores, following the two original questionnaire files.


## Findings

### On specification-driven development in this repository

The `spec/` directory functions as the specification for the artifact, not as
the artifact. The pattern observed in the pre-existing files:

* One file per concept, named for the concept.
* Prose definition first, then enumerated structure, then application notes,
  then limitations, then numbered sources.
* Paired `*-questionnaire.md` files turn a descriptive model into an
  operational instrument with 1–5 rating scales.

This is worth preserving and extending: the *model file* explains, the
*questionnaire file* operationalizes. The pairing is the repository's most
distinctive asset, because most public OD writing stops at explanation.

### On organizational development as a field

* **OD is not change management.** OD is the broader discipline of building an
  organization's capability to adapt; change management is the narrower practice
  of moving a population from one defined state to another. Most confusion in
  practice comes from applying a change-management tool (ADKAR, Kotter) to what
  is actually an OD problem (the organization cannot learn), or vice versa.

* **OD is not organization design.** Design is structural: operating models,
  reporting lines, decision rights. Development is behavioral: values, norms,
  team dynamics. The two are complements; most real programs need both, and
  most failures come from doing only design.

* **The field has a diagnosis deficit.** Practitioners reach for interventions
  (offsites, training, restructures) before diagnosis. The diagnostic model
  chapter is therefore load-bearing for the guide, and should come before the
  intervention catalog.

* **Transformational vs. transactional is the single most useful distinction.**
  Burke-Litwin's separation explains the most common failure in the field:
  applying a transactional fix (reorg, new tool, new policy) to a
  transformational problem (culture, leadership, mission).

* **The three target audiences share more than they differ.** All three are
  knowledge-work settings with high autonomy, high interdependence, high
  consequence of error, and professional identities that outrank organizational
  identity. A physician, a staff engineer, and a CTO all resist change that
  threatens professional judgment. This is the through-line for the guide.

* **Audience-specific pressures worth naming:**
  * *Health care*: safety and harm, shift-based work with no shared meeting
    time, strict hierarchy alongside licensure-based autonomy, regulation,
    burnout, and the fact that the customer can die.
  * *Software*: Conway's law, delivery pressure, on-call load, rapid
    technology churn, remote and hybrid distribution, and tooling that
    encodes process.
  * *Executive*: board and investor expectations, portfolio-level tradeoffs,
    succession, the distortion of information as it travels up, and the fact
    that the executive is usually the intervention's subject and its sponsor.

* **Evidence quality varies enormously across popular models.** Psychological
  safety, self-determination theory, and job characteristics have substantial
  empirical support. Kübler-Ross applied to organizations, Tuckman's stages,
  and most maturity models have little. The guide should say so plainly rather
  than presenting all models as equally sound; this is a differentiator.

* **Measurement is where OD programs die.** Programs are launched with no
  baseline, no control comparison, and lagging-only metrics. A dedicated
  measurement chapter with leading indicators and a warning about survey
  misuse is essential.


## Deliverable outline

`README.md` sections, in order:

1. **Introduction** — what this is, who it is for, how to use it.
2. **Foundations** — what OD is and is not; adjacent disciplines; values and
   ethics; evidence-based practice; systems thinking.
3. **The OD process** — entry and contracting, diagnosis, feedback,
   intervention design, implementation, evaluation, sustaining, exit.
4. **Diagnostic frameworks** — how to choose; then each model.
5. **Change frameworks** — how to choose; then each model.
6. **Culture** — what culture is, how to read it, how to change it.
7. **Teams and individuals** — safety, team models, motivation, learning.
8. **Interventions** — catalog by family; large-group methods; facilitation.
9. **Measurement** — what to measure, leading vs. lagging, survey practice,
   domain metric sets, evaluating an OD program honestly.
10. **Where to start** — a compact role-based decision aid.
11. **Anti-patterns** — the recurring failure modes, with tells and remedies.
12. **Questionnaires and templates** — inline, copy-paste ready.
13. **Glossary**.
14. **See also** — spec files and related repositories.


## Spec file inventory

Legend: `[x]` written, `[ ]` planned.

### Foundations, process, ethics

* [x] `od-process-cycle.md`
* [x] `entry-and-contracting.md`
* [x] `action-research.md`
* [x] `evidence-based-practice.md`
* [x] `od-ethics.md`
* [x] `systems-thinking.md`
* [x] `sociotechnical-systems.md`
* [x] `conways-law.md`
* [x] `interventions-catalog.md`

### Diagnostic models

Each is paired with a questionnaire of the same name plus `-questionnaire`.

* [x] `mckinsey-7s-framework.md` · [x] `-questionnaire.md`
* [x] `burke-litwin-causal-model.md` · [x] `-questionnaire.md`
* [x] `weisbord-six-box-model.md` · [x] `-questionnaire.md`
* [x] `nadler-tushman-congruence-model.md` · [x] `-questionnaire.md`
* [x] `galbraith-star-model.md` · [x] `-questionnaire.md`
* [x] `leavitt-diamond-model.md` · [x] `-questionnaire.md`
* [x] `maturity-models.md` · [x] `-questionnaire.md`
* [x] `force-field-analysis.md` · [x] `-questionnaire.md`
* [x] `swot-analysis.md` · [x] `-questionnaire.md`
* [x] `pestle-analysis.md` · [x] `-questionnaire.md`
* [x] `cynefin-framework.md` · [x] `-questionnaire.md`
* [x] `viable-system-model.md` · [x] `-questionnaire.md`
* [x] `organizational-network-analysis.md` · [x] `-questionnaire.md`
* [x] `team-topologies.md` · [x] `-questionnaire.md`

Some questionnaires depart from the plain 1–5 rating form where that form would
be dishonest, and say so in the file:

* `leavitt-diamond-model-questionnaire.md` inverts the scale — a high score is
  a warning about an unplanned second-order effect, not a good result.
* `maturity-models-questionnaire.md` has two parts: a generic capability
  self-assessment, and a critical appraisal of any maturity model you have been
  handed, because appraising the model matters at least as much as scoring
  against it.
* `swot-analysis-questionnaire.md` and `pestle-analysis-questionnaire.md` are
  worksheets with evidence and confidence columns, since the value is in the
  TOWS pairing and the impact-versus-confidence plot rather than in a score.
* `force-field-analysis-questionnaire.md` rates the strength of each force and
  requires a named owner per restraining force.
* `cynefin-framework-questionnaire.md` places a situation in a domain rather
  than scoring a scale, then checks the domain against the management approach
  actually in use.
* `organizational-network-analysis-questionnaire.md` has a practitioner ethics
  and readiness check that must be completed *before* the participant survey,
  with two items that are hard stops rather than trade-offs.

### Change models

* [x] `lewin-change-model.md`
* [x] `kotter-8-step-change-model.md`
* [x] `adkar-change-management-model.md`
* [x] `bridges-transition-model.md`
* [x] `kubler-ross-change-curve.md`
* [x] `satir-change-model.md`
* [x] `beckhard-harris-change-equation.md`
* [x] `rogers-diffusion-of-innovations.md`
* [x] `switch-framework.md`
* [x] `mckinsey-influence-model.md`
* [x] `theory-of-change.md`
* [x] `plan-do-study-act.md`
* [x] `improvement-kata.md`

### Culture, team, and human models

* [x] `schein-model-of-organizational-culture.md`
* [x] `competing-values-framework.md`
* [x] `westrum-organizational-culture-typology.md`
* [x] `hofstede-cultural-dimensions.md`
* [x] `just-culture.md`
* [x] `psychological-safety.md`
* [x] `tuckman-stages-of-group-development.md`
* [x] `lencioni-five-dysfunctions-of-a-team.md`
* [x] `drexler-sibbet-team-performance-model.md`
* [x] `google-project-aristotle.md`
* [x] `crew-resource-management.md`
* [x] `thomas-kilmann-conflict-modes.md`
* [x] `self-determination-theory.md`
* [x] `herzberg-two-factor-theory.md`
* [x] `maslow-hierarchy-of-needs.md`
* [x] `job-characteristics-model.md`
* [x] `immunity-to-change.md`
* [x] `situational-leadership-model.md`
* [x] `learning-organization.md`
* [x] `double-loop-learning.md`
* [x] `process-consultation.md`

### Large-group and facilitation methods

* [x] `appreciative-inquiry.md`
* [x] `open-space-technology.md`
* [x] `world-cafe.md`
* [x] `future-search.md`
* [x] `after-action-review.md`
* [x] `survey-feedback-method.md`

### Measurement

* [x] `measurement-and-metrics.md`
* [x] `employee-engagement-surveys.md`
* [x] `dora-metrics.md`
* [x] `space-framework.md`
* [x] `high-reliability-organizations.md`


## Tasks

* [x] Read existing spec files and infer conventions.
* [x] Confirm structure, audience handling, coverage, and style with the owner.
* [x] Write `spec/index.md` as the plan of record.
* [x] Write one spec file per model, framework, method, and system.
* [x] Write `README.md` as the comprehensive guide.
* [x] Label evidence strength on every model, framework, method, and system
      file, saying plainly where it is strong and where it is weak.
* [x] Add a questionnaire file for each diagnostic model, matching the two
      existing questionnaires, and cross-link each model to its questionnaire.
* [x] Add a `LICENSE.md`.
* [ ] Optional: add worked case studies, one per audience, running a single
      scenario end to end through the OD process.
* [ ] Optional: add a `CONTRIBUTING.md`.
* [ ] Optional: split the culture and team instruments already embedded in
      their model files — the psychological safety seven-item scale, the
      Westrum six-item scale, and the Edmondson safety/accountability grid —
      into standalone `-questionnaire.md` files, for symmetry with the
      diagnostic family.
* [ ] Optional: add a short `evidence.md` summarizing all labels in one table,
      so a reader can see the whole distribution without opening 68 files.


## Suggested improvements

Recorded here rather than acted on, so the owner can choose.

1. ~~**Pair every diagnostic model with a questionnaire.**~~ **Done.** All
   fourteen diagnostic models now have a paired questionnaire, cross-linked
   from a `## Questionnaire` section in the model file. The culture and team
   instruments — psychological safety, Westrum — remain embedded in their model
   files rather than split out; see the optional task above.

2. **Add a "choosing" decision table at the top of each family.** Readers do
   not need twelve diagnostic models; they need to pick one in five minutes.
   Implemented in `README.md`; could be pulled into spec files too.

3. ~~**Label evidence strength on every model.**~~ **Done.** Every model file
   now carries an `**Evidence:**` block stating plainly what is supported and
   what is not. This is the repository's clearest point of difference from
   typical OD content, most of which presents every framework as equally sound.
   Note the distribution is unflattering to the field: 20 files are flatly
   `Weak` and only 4 are `Strong`. That is an accurate picture, and it should
   not be softened.

4. **Cross-link to the owner's related repositories** rather than duplicating
   them: ADKAR, maturity models, company culture, OKRs, KPIs, KRIs, decision
   records, stakeholder analysis, value stream mapping, and others.

5. **Add anti-patterns as first-class content.** Most OD guides describe what
   to do. Describing the recognizable failure modes, with their tells, is more
   useful to a practitioner who has inherited a mess.

6. **Consider a one-page printable "OD canvas"** that walks a team from
   presenting problem, to diagnosis, to hypothesis, to intervention, to
   measure. This would make the repository operational for a workshop.

7. **Add worked end-to-end case studies**, one per audience, so readers see a
   full cycle rather than isolated frameworks.


## Open questions

* Should the guide keep the legacy HTML comment header block (browser, tracker,
  version, updated, contact, options) used in older repositories? It is omitted
  for now in new files.
* Should `README.md` include images or diagrams? Currently text-only for
  portability and diff-friendliness.
* Should the evidence labels be surfaced in `README.md` per model, or is the
  single summary table in the Foundations chapter sufficient? Currently the
  README carries the summary table and states the strength inline for the
  models where it changes how the model should be used.
* Should culture and team instruments be split into `-questionnaire.md` files
  too, or does the diagnostic family alone satisfy the pairing convention?


## Resolved

* **Questionnaire pairing** — resolved 2026-08-12: yes, every diagnostic model
  gets one. Twelve new questionnaires written.
* **Evidence labelling** — resolved 2026-08-12: yes, on every model file, with
  the plain statement rather than a bare rating.
* **License** — resolved 2026-08-12: `LICENSE.md` added by the repository owner.
