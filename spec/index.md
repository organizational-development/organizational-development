# Organizational Development — specification index

This directory is the working specification for the repository. The deliverable
is the top-level `README.md`: a comprehensive, self-contained organizational
development (OD) guide for knowledge workers.

Contents:

* [Original prompt](#original-prompt)
* [Decisions](#decisions)
* [Findings](#findings)
* [Repository layout](#repository-layout)
  * [Downstream: the website](#downstream-the-website)
* [Deliverable outline](#deliverable-outline)
* [Topic inventory](#topic-inventory)
* [Tasks](#tasks)
* [Suggested improvements](#suggested-improvements)
* [Open questions](#open-questions)
* [Resolved](#resolved)


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

- Add more files, one per model, or framework, or system, etc.
- Cover the "Process, measurement & ethics" family in full.
- Label evidence strength on every model, and say plainly where it is strong or
  weak.
- Give every diagnostic model a paired `*-questionnaire`.
- Reorganize into `topics/[topic]/index.md`, with `README.md` symlinked to
  `index.md` in each topic directory.


## Decisions

Decisions confirmed with the repository owner:

* **Structure**: `README.md` is a self-contained comprehensive guide. A reader
  should be able to act without following any link. `topics/` holds one
  directory per model, framework, method, or system; `spec/` holds the working
  notes, the plan of record, and the conventions.

* **Audience handling**: interleave concrete examples from all three audiences
  throughout the body, rather than segregating audiences into separate chapters.
  Every substantial model gets health care, software, and executive examples.

* **Coverage**: all four framework families.
  1. Diagnostic models.
  2. Change models.
  3. Culture, team, and human models.
  4. Process, measurement, and ethics.

* **Style**: house style plus depth. Terse bullet-driven sections, bold
  lead-ins, heavy linking, `See ...` references — but with enough explanation,
  tables, and worked examples that the guide teaches rather than merely indexes.

* **Conventions**: kebab-case filenames; one topic per directory; each topic
  file carries a short definition, an origin, the model content, a "When to use
  / when not to use" pair, limitations, and sources.

* **Evidence labelling**: every model, framework, method, and system file
  carries a `**Evidence: <strength>.**` block placed immediately before the "Use
  when" line. It states plainly what is supported, what is not, and what the
  specific methodological objections are. Strength values in use, from strongest
  to weakest: `Strong`, `Good`, `Moderate`, `Mixed`, `Contested`, `Weak`,
  `Very weak`, plus split labels of the form "Weak as a model, moderate in
  components" where a blanket rating would mislead, and `Not an empirical model`
  for taxonomies, checklists, methods, and normative material. The current
  distribution across 72 labelled files is 5 Strong, 6 Good, 9 Moderate, 5
  Mixed, 1 Contested, 20 Weak, 2 Very weak, plus 17 split labels and 7
  non-empirical.

* **Questionnaire pairing**: every diagnostic model has a paired
  `topics/<model>-questionnaire/` operational instrument, cross-linked from a
  `## Questionnaire` section in the model file. Questionnaires use a 1–5 rating
  scale, numbered steps, and a closing analysis step that says how to read the
  scores, following the two original questionnaire files.


## Findings

### On specification-driven development in this repository

The `spec/` directory is the specification for the artifact, not the artifact.
The artifact is `README.md`, with `topics/` as its reference layer.

The pattern inferred from the original files, and since made explicit in
[conventions.md](conventions.md):

* One file per concept, named for the concept.
* Prose definition first, then enumerated structure, then application notes,
  then limitations, then sources.
* Paired `*-questionnaire` files turn a descriptive model into an operational
  instrument with 1–5 rating scales.

This was worth preserving and extending: the *model file* explains, the
*questionnaire file* operationalizes. The pairing is the repository's most
distinctive asset, because most public OD writing stops at explanation.

Three things were added to make the specification enforceable rather than merely
descriptive, which is what "single source of truth" requires in practice:

* **[conventions.md](conventions.md)** states every rule once. Other files link
  to it instead of restating it, so there is nothing to drift.
* **`bin/audit`** turns the rules into 19 mechanical checks that exit non-zero.
  A convention nothing enforces decays; this one now fails loudly.
* **[../AGENTS.md](../AGENTS.md) and [../AGENTS/](../AGENTS/)** give agents the
  procedure without duplicating the rules. `CLAUDE.md` holds no content of its
  own and points at `AGENTS.md`.

The test applied throughout: if a fact appears in two files, one of them is
wrong eventually. The topic inventory was duplicated between this file and
`topics/index.md`, so it was removed from here.

### On organizational development as a field

* **OD is not change management.** OD is the broader discipline of building an
  organization's capability to adapt; change management is the narrower practice
  of moving a population from one defined state to another. Most confusion in
  practice comes from applying a change-management tool (ADKAR, Kotter) to what
  is actually an OD problem (the organization cannot learn), or vice versa.

* **OD is not organization design.** Design is structural: operating models,
  reporting lines, decision rights. Development is behavioral: values, norms,
  team dynamics. The two are complements; most real programs need both, and most
  failures come from doing only design.

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
  empirical support. Kübler-Ross applied to organizations, Tuckman's stages, and
  most maturity models have little. The guide should say so plainly rather than
  presenting all models as equally sound; this is a differentiator.

* **Measurement is where OD programs die.** Programs are launched with no
  baseline, no control comparison, and lagging-only metrics. A dedicated
  measurement chapter with leading indicators and a warning about survey misuse
  is essential.


## Repository layout

```
README.md              The deliverable: comprehensive self-contained guide
AGENTS.md              Operational entry point for coding agents
CLAUDE.md              Pointer to AGENTS.md; holds no content of its own
CONTRIBUTING.md        The same ground as AGENTS.md, for human contributors
CITATION.cff           Citation metadata
LICENSE.md             License
AGENTS/                Task playbooks: add-a-topic, add-a-questionnaire,
                       evidence-labels, style-guide, audit
bin/audit              Validation script; exits non-zero on any violation
.github/workflows/     CI: audit.yml runs bin/audit on push and pull request
spec/index.md          This file: the plan of record
spec/conventions.md    Single source of truth for how the repo is built
spec/ideas.md          Raw research notes, pre-synthesis
topics/index.md        Canonical inventory of all topics
topics/<name>/index.md One directory per model, framework, method, system
topics/<name>/README.md -> index.md
```

**Single source of truth.** Each fact lives in exactly one place:

| Fact | Canonical location |
| --- | --- |
| How the repository is built | [conventions.md](conventions.md) |
| What was decided and why | This file |
| What topics exist | [../topics/index.md](../topics/index.md) |
| What a model says | Its own `topics/<name>/index.md` |
| How an agent should work here | [../AGENTS.md](../AGENTS.md) |
| Whether the repository is valid | `bin/audit` |
| How the published site is built | Its own repository; see [below](#downstream-the-website) |

Files that need a fact link to its canonical location rather than restating it.
`CLAUDE.md` deliberately contains no guidance of its own; it points at
`AGENTS.md`. `AGENTS.md` does not restate conventions; it points at
`conventions.md`. This file does not restate the topic inventory; it points at
`topics/index.md`.

**Why the symlinks.** Each topic directory has `index.md` as the real file and
`README.md` as a symlink to it, so that GitHub renders the content when a
visitor opens the directory, while `index.md` stays canonical for tooling.


### Downstream: the website

The guide is published at <https://organizational-development.github.io>, built
from <https://github.com/organizational-development/organizational-development.github.io>
with SvelteKit, the Lily Design System, and `@sveltejs/adapter-static`.

**That repository vendors this one.** It holds a copy of `README.md` and of
every `topics/<name>/index.md` under `src/content/`, refreshed by running
`pnpm sync` there. Nothing in this repository has to change when the site
changes, but three things here are load-bearing for it, and breaking them
breaks the site quietly rather than loudly:

* **Heading text is a URL.** The site splits `README.md` into one page per
  `## ` part and rewrites every `#anchor` cross-reference to the page that now
  holds it. It reproduces GitHub's slug algorithm to do so. Renaming a heading
  moves an anchor; the site's build reports it as a `handleMissingId` warning
  rather than failing, so it is worth reading the build output after a rename.
* **Topic families come from `topics/index.md`.** The site's family manifest is
  keyed to the seven families and their order. A topic added here without being
  listed there still gets a page, but lands in an "Additional topics" bucket.
* **The `**Evidence: <strength>.**` block is parsed, not just displayed.** The
  site reads the leading strength value to rank the evidence table and colour
  the badge. A new strength value needs adding in three places: this
  repository's `conventions.md` and `bin/audit`, and the site's
  `src/lib/content.ts`.

The site is a *consumer*, not a second source of truth. When the two disagree,
this repository wins and the site is stale — run `pnpm sync` there.

## Deliverable outline

`README.md` sections, in order:

1. **Introduction** — what this is, who it is for, how to use it.
2. **Foundations** — what OD is and is not; adjacent disciplines; values and
   ethics; evidence-based practice; systems thinking.
3. **The OD process** — entry and contracting, diagnosis, feedback, intervention
   design, implementation, evaluation, sustaining, exit.
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


## Topic inventory

**The canonical inventory is [../topics/index.md](../topics/index.md).** It
lists every topic, grouped by family, with each model's evidence label and a
one-line description. It is not duplicated here, because a second copy would
drift.

Current counts, as verified by `bin/audit`:

| | Count |
| --- | --- |
| Topic directories | 88 |
| Model, framework, method, and system topics | 72 |
| Paired questionnaires | 16 |
| Diagnostic models, all paired | 14 |
| Culture and team models with a validated instrument, both paired | 2 |

Families, in the order used by `topics/index.md` and by the guide:

1. Foundations, process, and ethics — 10 topics
2. Diagnostic models — 14 topics, each with a questionnaire
3. Change models — 13 topics
4. Culture models — 5 topics, one with a questionnaire
5. Team and individual models — 19 topics, one with a questionnaire
6. Facilitation and large-group methods — 6 topics
7. Measurement — 5 topics

Questionnaires that depart from the plain 1–5 rating form, because that form
would be dishonest for them, are documented in
[conventions.md](conventions.md#questionnaire-pairing) with the reason for each
departure.

## Tasks

* [x] Read existing spec files and infer conventions.
* [x] Confirm structure, audience handling, coverage, and style with the owner.
* [x] Write `spec/index.md` as the plan of record.
* [x] Write one file per model, framework, method, and system.
* [x] Write `README.md` as the comprehensive guide.
* [x] Label evidence strength on every model, framework, method, and system
      file, saying plainly where it is strong and where it is weak.
* [x] Add a questionnaire file for each diagnostic model, matching the two
      existing questionnaires, and cross-link each model to its questionnaire.
* [x] Add a `LICENSE.md`. Added by the repository owner.
* [x] Add a `CITATION.cff`. Added by the repository owner.
* [x] Reorganize into `topics/[topic]/index.md`, with `README.md` symlinked to
      `index.md` in every topic directory. Done by the repository owner;
      all 373 cross-topic links and 150 README links rewritten to the
      `../<topic>/` and `topics/<topic>/` directory forms.
* [x] Write `spec/conventions.md` as the single source of truth, and make every
      other file defer to it rather than restate it.
* [x] Write `bin/audit` to enforce the conventions mechanically; 19 checks,
      run in CI on push and pull request.
* [x] Write `AGENTS.md`, `CLAUDE.md`, and the five `AGENTS/` playbooks, each
      under the 40 KB budget.
* [x] Write `topics/index.md` as the canonical topic inventory, and remove the
      duplicate inventory from this file.
* [x] Harmonize the seven pre-existing files that predated the conventions:
      add `Use when` and `Do not use when` to the five model files, and
      evidence labels, back-links, and analysis sections to the two original
      questionnaires.
* [x] Add worked case studies, one per audience, running a single scenario end
      to end through the OD process. In `README.md`, Part 12.
* [x] Add a `CONTRIBUTING.md` for human contributors, complementing `AGENTS/`.
* [x] Split the two culture and team instruments into standalone questionnaire
      topics: `psychological-safety-questionnaire` and
      `westrum-organizational-culture-typology-questionnaire`. These are the
      best-evidenced constructs in the collection, so they earned it most. Each
      goes beyond the scale already in `README.md`: psychological safety adds
      the safety-and-accountability grid and six behavioral indicators; Westrum
      adds a seven-dimension placement grid and six behavioral checks. The
      convention was tightened at the same time — a questionnaire requires a
      real published instrument behind it, so the rest of the culture and team
      family does not get one.
* [x] Add a CI workflow running `bin/audit` on push and pull request, so the
      invariants are enforced without relying on anyone remembering. It also
      publishes the evidence label distribution to the job summary, which makes
      an accidental drift toward generosity visible.
* [x] Coverage audit against the guide's own claims, 2026-08-13. Cross-checked
      every model named in the `README.md` evidence table, and every concept
      referenced across two or more topic files, against the topics that exist.
      Four genuine gaps found and filled:
      * `goal-setting-theory` — rated `Strong` in the evidence table and
        referenced in four topics, with no file. The worst of the four, because
        it is among the best-supported findings in the field.
      * `burnout` — referenced in eight topics, central to the health care
        audience, with no file.
      * `transformational-leadership` — rated `Moderate` in the table,
        referenced in two topics, with no file.
      * `discredited-instruments` — learning styles and MBTI appeared in the
        evidence table as refuted and weak, with nowhere to send a reader who
        needs the specific objection. Now covers those plus DISC, generational
        categories, graphology, and NLP.
      `bin/audit` check 13 was added so this class of drift fails loudly rather
      than waiting for the next manual pass.
* [x] Conventions compliance audit, 2026-08-13. Verified the conventions this
      repository asserts but had never checked. Four were being violated:
      * **178 lines over 80 columns**, concentrated in the pre-existing files
        and in `README.md`. All prose rewrapped. Two structural bugs surfaced
        and were fixed in the process: a missing blank line before one
        `**Evidence:` block, which had merged it into the definition paragraph;
        and inline code spans being split across lines.
      * **Six model topics had no `## Examples by audience` section.** Two were
        heading-name drift (`## Beyond software`, `## Applying it beyond
        software`) and were renamed; four genuinely had none and were written.
      * **Three orphan topics** that no sibling linked to, including two added
        the same day — `discredited-instruments`, `transformational-leadership`,
        and `hofstede-cultural-dimensions`. This violated the rule stated in
        `AGENTS/add-a-topic.md`, which shows how quickly an unenforced
        convention decays.
      * Checks 14, 15, and 16 added so none of these can recur. `spec/ideas.md`
        is exempt from wrapping as raw pre-synthesis notes.
* [x] Merge conflict resolution, 2026-08-13. An interactive rebase replaying
      `fcc650c` onto `23a161d` — two versions of the same "Add topics" work —
      left 93 conflicts across 84 files. `git status` reported "all conflicts
      fixed" with zero unmerged paths, because the files had been staged with
      the markers still in them. Resolved by taking the incoming side, after
      verifying word-by-word that it was a superset: the six files where the
      HEAD side had unique words were all deliberate renames, rewrites, and
      count updates. Verified afterwards by audit, link check, and spot checks
      that no content was lost.
* [x] Accuracy pass, 2026-08-13. Scanned every stated number against ground
      truth and found five drifts, all introduced by earlier work in this
      sequence:
      * `README.md` claimed `bin/audit` had 11 checks; it had 16.
      * `spec/index.md` said "84 topics" after the count reached 88.
      * Two family counts here were stale: foundations 9 → 10, team and
        individual 16 → 19.
      * The validation list in `conventions.md` had 15 checks listed against 16
        in the script, having silently collapsed two link checks into one.
      * Two references still used the pre-`topics/` naming: "each spec file" and
        `<model>-questionnaire.md`.
      Check 17 was added in response to the fourth: it compares the documented
      check list against the `section` calls in `bin/audit`, item by item, so
      the conventions file cannot describe a script that does not exist. This
      makes the single-source-of-truth claim enforceable rather than
      aspirational for the one file whose whole purpose is to be that source.
* [x] Self-documentation audit, 2026-08-13. Checked every claim the repository
      makes *about itself* against the tree, after two passes the same day had
      each changed the check count. Three defects, all in the files an agent
      reads when something has already gone wrong:
      * **`AGENTS/audit.md` documented 11 checks against 17 in the script.**
        Checks 12 to 17 had no table row and no fix instructions, which is the
        worst place for a stale fact: it is the file you open *because* a check
        just failed. Rows and fix entries written for all of them.
      * **The documented recount command counted questionnaires.** Every stated
        distribution is model-only — 72 files, 20 `Weak`, 5 `Strong` — but the
        published command returned 88 files, 25 `Weak`, 6 `Strong`. Anyone
        following the documented procedure would have "corrected" the tables to
        the wrong numbers. Fixed in all four files that carry it, with a note
        saying why questionnaires are excluded.
      * **The stale "68 labels" in suggested improvement 9**, left behind when
        the count reached 72.
      Checks 18 and 19 added: `AGENTS/audit.md` must document every check, and
      every "<n> checks" claim in prose must match the script. Check 19 skips
      past-tense lines so that the historical records above can stay; write
      history in the past tense and current fact in the present.
* [x] Record the published website in the specification, 2026-08-13. The site
      at <https://organizational-development.github.io> vendors this repository
      and had been documented nowhere here, so nothing said which facts it
      depends on. Now under [Downstream: the
      website](#downstream-the-website), with the three couplings that break it
      quietly: heading text is a URL, families come from `topics/index.md`, and
      the evidence strength value is parsed rather than merely displayed.
* [x] Evidence review pass 1, 2026-08-13. First review of the 72 labels since
      they were written on 2026-08-12. Method: read every label and its
      justification; check each questionnaire against the model it
      operationalizes; check the `README.md` evidence summary table against the
      topic files; then check the most specific empirical claims, and the
      ratings most likely to have moved, against current literature.
      Findings:
      * **Verified and unchanged.** The summary table agrees with every topic
        label. All 16 questionnaires carry their model's rating. The after
        action review claim of a 20 to 25 percent performance improvement
        matches the debrief meta-analysis it comes from. Learning styles remain
        refuted. The DORA speed-and-stability finding was reconfirmed in the
        2025 report.
      * **One rating changed.** `competing-values-framework` moved from
        `Moderate to good` to `Moderate as a vocabulary, mixed as an
        instrument`. The old label praised the OCAI's psychometrics without
        mentioning that the standard form is ipsative — respondents divide 100
        points across four types — which manufactures negative correlations
        between scales and makes factor analysis and cross-unit comparison
        unsound. This collection already downgrades the TKI for exactly that
        property, so the old rating was internally inconsistent as well as
        generous. Validation work with Likert adaptations has also found the
        diagonal types positively correlated where the framework predicts
        opposition, which challenges the "competing" premise itself.
      * **One topic was out of date on fact rather than rating.**
        `dora-metrics` described four metrics; DORA now publishes five, grouped
        as throughput and instability, with rework rate added and time to
        restore service renamed to failed deployment recovery time. The AI
        finding — higher throughput and higher instability together — is new,
        practically important for this guide's software audience, and flagged
        as the least settled result in that file.
      * **One caveat added.** `psychological-safety` keeps `Strong`, which the
        meta-analytic evidence supports, but now says that the measures have
        multiplied faster than the construct has been pinned down, so scores
        from different instruments are not comparable.
      No rating was softened. The distribution is unchanged: the competing
      values move was from one split label to another.
* [ ] Optional: evidence review pass 2, due 2027-08. Same method. Watch in
      particular for movement on `transformational-leadership`, where the
      measurement critique is live, and on `dora-metrics`, where the AI results
      rest on a small number of annual cohorts.
* [ ] Optional: make the diagnosis one-pager in `README.md` Part 11 genuinely
      printable, and test it in a real workshop. See suggested improvement 6.


## Suggested improvements

Recorded here rather than acted on, so the owner can choose.

1. ~~**Pair every diagnostic model with a questionnaire.**~~ **Done.** All
   fourteen diagnostic models have a paired questionnaire, cross-linked from a
   `## Questionnaire` section in the model file, plus the two culture and team
   models that carry validated published instruments. Sixteen in total. The
   convention now states the test explicitly: a questionnaire requires a real
   instrument behind it, so Tuckman and Lencioni do not get one — offering a
   rating scale for a model with no psychometric basis would undercut the
   honesty the evidence labels exist to preserve.

2. **Add a "choosing" decision table at the top of each family.** Readers do not
   need twelve diagnostic models; they need to pick one in five minutes.
   Implemented in `README.md`; could be pulled into spec files too.

3. ~~**Label evidence strength on every model.**~~ **Done.** Every model file
   now carries an `**Evidence:**` block stating plainly what is supported and
   what is not. This is the repository's clearest point of difference from
   typical OD content, most of which presents every framework as equally sound.
   Note the distribution is unflattering to the field: 20 files are flatly
   `Weak` and only 5 are `Strong`. That is an accurate picture, and it should
   not be softened.

4. ~~**Cross-link to the owner's related repositories**~~ **Done.** Twenty
   related repositories are linked from `README.md` rather than duplicated:
   ADKAR, maturity models, company culture, OKRs, KPIs, KRIs, decision records,
   stakeholder analysis, value stream mapping, and others.

5. ~~**Add anti-patterns as first-class content.**~~ **Done.** `README.md` Part
   10 covers fifteen recurring failure modes, each with its tell and its remedy.
   This is aimed at the practitioner who has inherited a mess rather than the
   one starting clean, and it is among the most-used parts of the guide for that
   reason.

6. **Consider a one-page printable "OD canvas"** that walks a team from
   presenting problem, to diagnosis, to hypothesis, to intervention, to measure.
   This would make the repository operational for a workshop. The diagnosis
   one-pager in `README.md` Part 11 is close to this already; the remaining work
   is making it printable and testing it in a real session.

7. ~~**Add worked end-to-end case studies**~~ **Done.** `README.md` Part 12 runs
   one scenario per audience through the full cycle: entry, contracting,
   diagnosis, feedback, intervention, measurement, and result — including what
   went wrong and what the team got wrong first.

8. ~~**Enforce the invariants in CI.**~~ **Done.** `.github/workflows/audit.yml`
   runs `bin/audit` on push to main, on every pull request, and on manual
   dispatch. It also prints the evidence label distribution to the job summary,
   so that a gradual drift toward generosity becomes visible in the pull request
   rather than only in a careful review.

9. ~~**Schedule an evidence review.**~~ **Done, and now recurring.** Ratings
   age as research appears, so an annual pass over the 72 labels is recorded in
   the task list with its date, method, and outcome. Pass 1 ran on 2026-08-13
   and changed one rating, corrected one topic that had gone out of date on
   fact rather than on evidence, and added one caveat. Pass 2 is due 2027-08.

10. **Consider a `topics/<name>/examples/` convention** for topics that
    accumulate more worked material than fits in one file — the pattern used in
    the maturity-models repository. Not needed yet at 88 topics, and worth
    deciding before it is.


## Open questions

* Should the guide keep the legacy HTML comment header block (browser, tracker,
  version, updated, contact, options) used in older repositories? It is omitted
  for now in new files.
* Should `README.md` include images or diagrams? Currently text-only for
  portability and diff-friendliness.
* Should the evidence labels be surfaced in `README.md` per model, or is the
  single summary table in the Foundations chapter sufficient? Currently the
  README carries the summary table and states the strength inline for the models
  where it changes how the model should be used.
* Should a failing audit block a merge? The CI workflow runs and reports;
  whether to make it a required status check is a repository setting the owner
  controls, and has not been enabled.
* Should the evidence review be annual, or triggered by a contributor
  challenging a specific label? The second is cheaper and depends on the
  repository having readers.


## Resolved

* **Repository layout** — resolved 2026-08-12: `topics/[topic]/index.md` with
  `README.md` symlinked to `index.md`, so directory links render on GitHub while
  `index.md` stays canonical for tooling.
* **Single source of truth** — resolved 2026-08-12: `spec/conventions.md` is
  authoritative for how the repository is built; every other file links to it
  rather than restating it. The topic inventory moved to `topics/index.md` and
  was removed from this file for the same reason.
* **Agent file budget** — resolved 2026-08-12: the 40 KB limit applies to
  `CLAUDE.md`, `AGENTS.md`, and `AGENTS/*`. `README.md` is exempt; it is the
  deliverable and is deliberately large and self-contained, at roughly 180 KB.
* **Questionnaire pairing** — resolved 2026-08-12: yes, every diagnostic model
  gets one. Twelve new questionnaires written. Extended 2026-08-13: the two
  culture and team models with validated published instruments get one as well.
  The test is whether a real instrument exists, not whether the model could be
  turned into a rating scale — most could, and should not be.
* **CI enforcement** — resolved 2026-08-13: `bin/audit` runs on push, pull
  request, and manual dispatch. Whether a failure blocks a merge is left to the
  repository owner as a branch protection setting.
* **Contributor documentation** — resolved 2026-08-13: `CONTRIBUTING.md` for
  humans, `AGENTS.md` and `AGENTS/` for agents. Both defer to `conventions.md`
  rather than restating it.
* **Evidence labelling** — resolved 2026-08-12: yes, on every model file, with
  the plain statement rather than a bare rating.
* **License** — resolved 2026-08-12: `LICENSE.md` added by the repository owner.
