# Playbook: add a questionnaire

Every diagnostic model has a paired questionnaire. The model file explains; the
questionnaire operationalizes. This pairing is the repository's most distinctive
asset, because most public OD writing stops at explanation.

Conventions in
[../spec/conventions.md](../spec/conventions.md#questionnaire-pairing).


## When one is required

* **Required** for every topic in the diagnostic family. All 14 have one.
* **Present** for two culture and team models that carry published, validated
  instruments and are the best-evidenced constructs here: `psychological-safety`
  and `westrum-organizational-culture-typology`.
* **Not appropriate** for the rest of the culture and team family, for change
  models, for facilitation methods, or for foundations. A questionnaire for
  Kotter or Tuckman would imply a precision those models do not have, and would
  undercut the honesty the evidence labels are there to preserve.

The test: **is there a real instrument behind it?** A published scale with
psychometric work behind it earns a questionnaire. A four-box model that someone
could be asked to rate does not.


## Create it

```sh
model=weisbord-six-box-model
mkdir -p "topics/$model-questionnaire"
cd "topics/$model-questionnaire"
$EDITOR index.md
ln -sfn index.md README.md
cd ../..
```

Then add to `topics/$model/index.md`, before its `## See also`:

```markdown
## Questionnaire

A paired, copy-and-use diagnostic instrument for this model:
[weisbord-six-box-model-questionnaire](../weisbord-six-box-model-questionnaire/).
```


## Default structure

```markdown
# Model Name Questionnaire

To run a <model> diagnostic, use this questionnaire. It evaluates <what>,
scoring from 1 (<low anchor>) to 5 (<high anchor>).

See [model-name](../model-name/).

**Evidence: <Strength>.** Carried over from the model, phrased for the
instrument: what the scores can and cannot support.

<Optional: how to run it — group size, duration, individual-first scoring.>


## Step 1: <First dimension>

1. <Item name>

- Question: <A question a real practitioner would ask out loud.>
  - Rating (1–5): [ ]

2. <Item name>

- Question: <...>
  - Rating (1–5): [ ]


## Step N: Analysis

* **<How to read the pattern.>**
* **<What the common failure signature looks like.>**
* **<What to do next, with a link to the follow-on instrument.>**
```

The `[ ]` is a literal checkbox for the reader to fill in. Keep it.


## The analysis section is mandatory

A questionnaire that produces numbers and does not say how to read them is worse
than no questionnaire, because it invites confident misreading.

A good analysis section answers:

* **What pattern matters?** Usually a gap, a spread, or a lowest score — rarely
  the average. Weisbord reads the formal-versus-informal gap; Beckhard-Harris
  reads any term at zero; the star model reads the lowest point.
* **What is the common failure signature?** Name the specific configuration you
  expect to see and what it means.
* **What do you do next?** Link to the follow-on instrument or intervention.
* **What must the reader not conclude?** State the misreading you expect.


## Departing from the default form

Depart when the default would be dishonest, and say so in the file. Established
departures:

| Departure | Where | Why |
| --- | --- | --- |
| Inverted scale — high score is a warning | `leavitt-diamond-model-questionnaire` | Measures disruption, not quality |
| Two parts: self-assessment plus critical appraisal of the model | `maturity-models-questionnaire` | Appraising the model matters as much as scoring against it |
| Worksheet with evidence and confidence columns | `swot-analysis-questionnaire`, `pestle-analysis-questionnaire` | Value is in the pairing or plotting step, not a score |
| Force ratings plus a mandatory named owner per item | `force-field-analysis-questionnaire` | Without an owner the analysis is decorative |
| Domain placement rather than scale scoring | `cynefin-framework-questionnaire` | The situation has a kind, not a level |
| Ethics gate before the participant survey, with hard stops | `organizational-network-analysis-questionnaire` | The data is capable of real harm |

If your instrument needs a new departure, add it to this table and to
`spec/conventions.md`.


## Writing good items

* **Ask what a practitioner would ask aloud.** "What actually gets someone
  promoted here?" beats "Rate the alignment of the reward system."
* **Ask about observable behavior**, not attitude. "In the last month, did you
  see a leader admit a mistake?" is harder to fake than "Do leaders model
  humility?"
* **One idea per item.** An item containing "and" usually scores the easier
  half.
* **Name the scale anchors** at both ends, in the words of the domain.
* **Score individually first, then compare.** Say so in the file. Divergence
  within a leadership team is frequently the most valuable output, and group
  scoring destroys it.
* **Keep it runnable.** Twelve to thirty items. Longer instruments are filled in
  carelessly or not at all.
* **Never ask about something you cannot act on.** That is extraction, and it
  lowers trust below the pre-survey baseline. See
  [../topics/od-ethics/](../topics/od-ethics/).


## Reporting rules to state in the file

Where the instrument touches individuals, restate the ethics constraints in the
questionnaire itself rather than assuming the reader followed a link:

* Report at team level and above; never individual level.
* Set a minimum response threshold, commonly five to ten.
* Never use results in performance, promotion, or redundancy decisions.
* Say who will read free-text comments verbatim, before collecting them.


## Validate

```sh
bin/audit
```

Check 5 verifies that the model has a `## Questionnaire` section, that the
questionnaire links back with `../<model>/`, and that it has a closing analysis
section.
