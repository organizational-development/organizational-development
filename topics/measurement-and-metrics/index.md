# Measurement and metrics for organizational development

Most OD programs are evaluated badly or not at all: no baseline, no comparison,
lagging indicators only, and a definition of success that shifts to match the
result. This file covers how to measure honestly.

**Evidence: Not a model — measurement guidance.** The components have different
pedigrees. Statistical process control and time-series analysis are formally
sound. Goodhart's law is an observation with abundant documented instances
rather than a theorem. Kirkpatrick's four levels are a widely used convention
with known weaknesses, chiefly that the levels are not causally linked as often
assumed. The staggered-rollout design advice reflects standard
quasi-experimental methodology and is well founded.

Use when: designing any program you will later be asked to justify.

Do not use when: measurement would cost more than the intervention, or would
distort the behavior more than it would inform. Both happen.


## Principles

* **Baseline first.** You cannot show change without a before. Collect it before
  the intervention is announced, because announcement is itself an intervention.
* **Predict, then measure.** Write down the expected direction and magnitude in
  advance. Retrospective interpretation always finds success.
* **Leading and lagging.** Lagging indicators (turnover, harm events, revenue)
  confirm; leading indicators (reporting rate, cycle time, participation) steer.
  You need both, and only the leading ones let you act in time.
* **Balancing measures.** What could this make worse? Every improvement can
  export harm. Measure the export.
* **Plot over time, not before-and-after.** Two bars cannot distinguish a real
  shift from normal variation. Use run charts or control charts. See
  [plan-do-study-act](../plan-do-study-act/).
* **Aggregate, do not surveil.** Team level and above. Individual-level OD
  metrics change behavior toward the metric and destroy the data. See
  [od-ethics](../od-ethics/).


## Categories of OD measure

| Category | Examples | Notes |
| --- | --- | --- |
| Perception | Engagement, psychological safety, Westrum, eNPS | Cheap, fast, gameable, subject to response bias |
| Behavior | Reporting rate, speaking-up incidents, meeting participation, review latency | Harder to collect, much harder to fake |
| Flow | Lead time, cycle time, queue length, work in progress | Objective; needs instrumented systems |
| Outcome | Harm events, defects, customer satisfaction, retention | What matters; slow, noisy, multi-causal |
| Capability | Cross-skilling, bus factor, time to onboard | Predicts resilience |
| Cost | Turnover cost, agency spend, rework, overtime | Speaks to finance; easy to overclaim |

Behavior measures are the most under-used and the most informative. "Did anyone
challenge a senior decision this month, and what happened to them?" is worth ten
survey items.


## Goodhart's law and metric distortion

"When a measure becomes a target, it ceases to be a good measure."

Predictable distortions:

* **Gaming**: hitting the number without the outcome. Four-hour emergency
  targets met by moving patients to a corridor reclassified as a ward.
* **Tunnel vision**: measured things improve, unmeasured things decay.
* **Effort substitution**: work shifts to what is counted.
* **Suppression**: reporting falls because reporting looks bad.

Countermeasures: use balanced sets rather than single numbers; pair every
efficiency measure with a quality measure; never tie individual pay to a single
OD metric; review what the metric would look like if gamed, and watch for that
signature.


## The reporting-rate paradox

The most important measurement trap in OD. When safety culture improves,
incident and near-miss reporting **rises**, because people are willing. When it
deteriorates, reporting falls.

A rising reporting rate is therefore success and looks like failure.

Agree the interpretation with the board *before* the data moves. Pair reporting
rate with a severity-weighted harm measure: reports up, serious harm flat or
down, is the signature of a healthy system. See
[psychological-safety](../psychological-safety/),
[westrum-organizational-culture-typology](../westrum-organizational-culture-typology/).


## Evaluating a program honestly

Kirkpatrick's four levels, applied to OD rather than training:

1. **Reaction**: did people find it useful? Nearly meaningless alone, and the
   only level most programs report.
2. **Learning**: did knowledge or attitudes change?
3. **Behavior**: is anyone doing anything differently, 90 days later? The level
   at which most programs are shown to have failed, which is why it is rarely
   measured.
4. **Results**: did the organizational outcome change?

Add a fifth question that Kirkpatrick does not: **would it have changed
anyway?** Options for causal confidence, in ascending order:

* Pre/post in one unit — weakest; confounded by everything.
* Pre/post with a comparison unit — much better, usually feasible.
* Staggered rollout, with units acting as their own controls — strong, and
  practical, since rollouts are staggered anyway.
* Randomized allocation of units — strongest, occasionally possible, and worth
  arguing for when the intervention is scarce and must be rationed regardless.

Stagger deliberately, and you get a natural experiment for free.


## Examples by audience

* **Health care**: pair harm outcomes (lagging) with reporting culture and
  staffing fill rates (leading). Use statistical process control, which is
  already standard in clinical improvement, rather than month-on-month
  comparison.

* **Software**: DORA metrics are flow and outcome measures with published
  benchmarks. See [dora-metrics](../dora-metrics/). Pair with
  [space-framework](../space-framework/) so that speed measures do not silently
  cost wellbeing.

* **Executive**: demand three things of any people program — the baseline, the
  prediction, and the balancing measure. Programs that cannot supply all three
  have not been designed, only purchased.


## See also

* [theory-of-change](../theory-of-change/)
* [evidence-based-practice](../evidence-based-practice/)
* <https://github.com/joelparkerhenderson/key-performance-indicator>
* <https://github.com/joelparkerhenderson/key-risk-indicator>
* <https://github.com/joelparkerhenderson/outputs-vs-outcomes>
