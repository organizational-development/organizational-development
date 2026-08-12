# Westrum organizational culture typology

Ron Westrum's typology classifies organizational culture by **how information
flows**, particularly information that someone would rather not hear. Developed
from studying safety-critical organizations — aviation, medicine, nuclear — it
has since been validated in software delivery research.

Westrum's central proposition: an organization's information flow is a proxy for
its overall functioning, because good information flow requires everything else
to be working.

**Evidence: Good.** Unusually strong for a culture model. Developed from
safety-critical industry case studies, then operationalized as a six-item scale
and validated in large-sample software delivery research, where generative
culture statistically predicts both delivery performance and organizational
performance. The evidence is correlational and self-report, and the typology
flattens what is really a continuum, but the construct-to-outcome chain is
better established here than almost anywhere else in this collection.

Use when: assessing whether an organization can learn from problems; predicting
whether risk information reaches decision-makers; measuring safety or delivery
culture with a short, validated instrument.

Do not use when: you need a full culture picture. This measures one dimension —
but it is the highest-value single dimension.


## The three types

| | **Pathological** | **Bureaucratic** | **Generative** |
| --- | --- | --- | --- |
| Orientation | Power | Rule | Performance |
| Cooperation | Low | Modest | High |
| Messengers | Shot | Neglected | Trained |
| Responsibilities | Shirked | Narrow | Shared |
| Bridging between units | Discouraged | Tolerated | Encouraged |
| Failure leads to | Scapegoating | Justice-seeking | Inquiry |
| Novelty leads to | Crushed | Problems | Implemented |

Read the columns as a whole. The rows co-occur: an organization that shoots
messengers also discourages bridging and crushes novelty, because all three
follow from a power orientation.


## Why "failure leads to inquiry" is the key row

In a pathological culture, the question after a failure is *who*. In a
bureaucratic culture, it is *which rule was broken*. In a generative culture, it
is *what about our system made this the reasonable thing to do*.

Only the third produces learning. The first two produce hidden information,
which is the precondition for the next, larger failure. See
[just-culture](../just-culture/).


## Evidence

Unusually strong for a culture model. Nicole Forsgren, Jez Humble, and Gene
Kim's DevOps research found Westrum generative culture statistically predicts
both software delivery performance and organizational performance, using a
six-item survey scale. This makes it one of the few culture constructs with a
demonstrated link to outcomes. See [dora-metrics](../dora-metrics/).


## The six-item measure

Rate agreement 1–7. Adapted from the published scale:

1. On my team, information is actively sought.
2. Messengers are not punished when they deliver news of failures or other bad
   news.
3. Responsibilities are shared.
4. Cross-functional collaboration is encouraged and rewarded.
5. Failure causes inquiry.
6. New ideas are welcomed.

Short enough to run quarterly. Report at team level and above; never per person.


## Moving toward generative

The type is produced by leader behavior, especially under pressure.

* Respond to bad news with curiosity and visible thanks — every time, including
  when the news is inconvenient and the messenger is annoying.
* Make failure reviews blameless by design and by facilitation, not by slogan.
  See [after-action-review](../after-action-review/).
* Reward the person who surfaces a problem early, publicly, in front of peers.
* Remove the mechanisms that punish disclosure: individual blame in incident
  reports, performance consequences for reporting, "no surprises" norms that
  actually mean "no bad news".
* Fund bridging: explicit boundary-spanning roles and cross-unit forums.

One senior leader who reacts badly to bad news once can undo a year of this.
That asymmetry is the whole problem.


## Examples by audience

* **Health care**: the classic domain. Wards with high near-miss reporting are
  usually safer, not more dangerous — a fact that must be established with
  boards *before* reporting rates rise, or the improvement will be read as
  deterioration and punished.

* **Software**: an incident review that ends with "human error" is a
  pathological or bureaucratic artifact. A generative review ends with changes
  to the system that made the error easy and its detection hard.

* **Executive**: measure how long it takes for bad news to reach you, and how
  distorted it is when it arrives. The distance between the front line and the
  executive is where information dies. Ask your directs what they did not tell
  you last quarter, and react well to the answer.


## Limitations

* Single dimension; will not describe values, identity, or purpose.
* Self-report; a genuinely pathological culture may report itself as generative
  out of fear, which is why the score should be read alongside behavior.
* Typology, so it flattens the continuum.


## Questionnaire

A paired, copy-and-use instrument for this model:
[westrum-organizational-culture-typology-questionnaire](../westrum-organizational-culture-typology-questionnaire/).
It carries the validated six-item scale, a placement grid across all seven
dimensions, and behavioral evidence to check the scale against.


## See also

* [psychological-safety](../psychological-safety/)
* [just-culture](../just-culture/)
* [high-reliability-organizations](../high-reliability-organizations/)
* Westrum, "A typology of organisational cultures", *Qual Saf Health Care*
  (2004).
