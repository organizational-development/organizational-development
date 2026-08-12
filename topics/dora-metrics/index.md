# DORA metrics

DORA (DevOps Research and Assessment) metrics come from a multi-year research
program led by Nicole Forsgren, Jez Humble, and Gene Kim, published in
*Accelerate* and the annual State of DevOps reports. They are relevant to OD
beyond software because the research established a statistical link between
**organizational culture** and **delivery performance**.

**Evidence: Good.** Large-sample, multi-year, repeatedly replicated across
annual cohorts, and the finding that speed and stability move together rather
than trading off has held up across many years of data. The evidence is
correlational and originally survey-based with self-selected respondents, so the
causal chain from culture to delivery to organizational performance is argued
rather than experimentally established. Strong by the standards of this field;
not a randomized trial.

Use when: measuring software delivery capability; making the case that culture
work has operational consequences.

Do not use when: comparing teams against each other for performance management.
This is the standard misuse and it destroys the metrics' value.


## The four key metrics

Two speed, two stability. The research finding is that they move **together**,
not in tension — high performers are better at all four simultaneously,
contradicting the assumption that speed trades against safety.

1. **Deployment frequency** — how often code is deployed to production.
2. **Lead time for changes** — from code committed to code running in
   production.
3. **Change failure rate** — percentage of deployments causing a degradation
   requiring remediation.
4. **Time to restore service** (originally MTTR) — how long to recover from a
   failure.

A fifth, **reliability** (or operational performance), was added later:
availability and performance against user expectations.


## Why this matters to OD

The research found that **Westrum generative culture** predicts software
delivery performance, and that delivery performance predicts organizational
performance — profitability, productivity, market share, and non-commercial
mission outcomes. See
[westrum-organizational-culture-typology](../westrum-organizational-culture-typology/).

This is one of the few places in the OD literature with a quantified chain from
a culture construct to a business outcome, on a large sample, across many
organizations. It is worth citing precisely for that reason.

Other organizational capabilities the research identified as predictive:

* Continuous delivery practices and trunk-based development.
* Loosely coupled architecture and team autonomy — teams able to change and
  deploy without coordinating with other teams. See
  [conways-law](../conways-law/), [team-topologies](../team-topologies/).
* Lightweight change approval; formal change approval boards were found to be
  *negatively* associated with performance, which is an uncomfortable and
  well-replicated finding.
* Learning culture, job satisfaction, and low burnout.
* Transformational leadership.


## Using them well

* **Team level, not individual.** Never per-person. There is no defensible
  individual DORA metric.
* **Trend, not target.** Set a direction, not a number to hit, and expect gaming
  if you set a number.
* **All four together.** Deployment frequency alone incentivizes trivial
  deployments; change failure rate alone incentivizes never shipping.
* **Instrument, do not survey.** Derive from the pipeline where possible.
* **Pair with human measures.** Speed achieved by burning people is not a win.
  See [space-framework](../space-framework/).


## The common misuses

* Ranking teams on a dashboard. Different teams have genuinely different
  constraints — regulated systems, embedded hardware, legacy platforms.
* Setting a deployment frequency target and watching teams split commits.
* Treating the metrics as the goal rather than as a signal about the system.
* Measuring them without changing anything that affects them — DORA metrics are
  outputs of architecture, process, and culture, and staring at them changes
  none of the three.


## Examples by audience

* **Health care**: clinical systems have real regulatory constraints, and the
  metrics still apply. Long lead times for a patient-safety-critical patch are a
  safety issue, not a caution. The question to ask a regulated team is which
  specific control requires the delay, and whether it can be automated.

* **Software**: the native domain. The highest-value diagnostic use is
  decomposing lead time into its waiting stages — code review queue, test
  execution, approval, release window — and attacking the largest. It is almost
  never the coding.

* **Executive**: DORA gives a board-legible number for engineering health, and
  the published benchmarks let you position honestly. Use it to fund removal of
  constraints, never to compare teams in a review.


## Limitations

* Software-specific; translating to other knowledge work requires defining an
  equivalent to "deployment", which is not always possible.
* Survey-based in the original research, with self-selected respondents.
* Correlational; the causal chain is argued rather than experimentally
  established.
* Easy to game, and gamed metrics look like improvement.


## See also

* [space-framework](../space-framework/)
* [westrum-organizational-culture-typology](../westrum-organizational-culture-typology/)
* [measurement-and-metrics](../measurement-and-metrics/)
* [transformational-leadership](../transformational-leadership/) — identified
  in the same research as predictive of delivery performance.
* Forsgren, Humble & Kim, *Accelerate*.
