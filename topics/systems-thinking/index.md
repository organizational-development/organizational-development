# Systems thinking

Systems thinking is the discipline of explaining behavior by structure rather
than by blame. A system's recurring behavior is produced by its stocks, flows,
feedback loops, and delays — not primarily by the character of the people in it.

**Evidence: Mixed.** The formal mechanics — stocks, flows, delays, oscillation
from delayed feedback — are demonstrable and mathematically well founded. The
system archetypes are descriptive heuristics with no validation; they are
pattern names, not findings. Causal loop diagrams are easy to draw and hard to
falsify, so treat any specific diagram as a hypothesis the group holds, not as
evidence.

Use when: a problem recurs after being "fixed", when local optimizations are
making the whole worse, or when everyone involved is competent and the outcome
is still bad.

Do not use when: the cause is genuinely local and simple.


## Core concepts

* **Stocks and flows**: stocks accumulate (backlog, staff, trust, technical
  debt); flows change them (hiring, attrition). Stocks change slowly and create
  inertia; most impatience in change programs is impatience with a stock.

* **Reinforcing loops (R)**: amplify change. Growth and collapse both come from
  reinforcing loops. Example: overload → errors → rework → more overload.

* **Balancing loops (B)**: resist change and seek a goal. Most resistance to a
  change program is a balancing loop doing its job, protecting something the
  system values.

* **Delays**: the gap between action and effect. Delays cause overshoot,
  oscillation, and the abandonment of interventions just before they work.
  Hiring, training, and culture change all have long delays.

* **Leverage points**: Donella Meadows ranked places to intervene. Low leverage:
  parameters, targets, numbers. High leverage: rules, information flows, goals,
  and the paradigm from which the system arises. Most management attention goes
  to the lowest-leverage end.


## Common system archetypes

* **Fixes that fail**: the quick fix works short term and worsens the problem
  long term. Adding people to a late project.
* **Shifting the burden**: a symptomatic fix atrophies the fundamental
  capability. Hiring contractors instead of building internal skill.
* **Limits to growth**: a reinforcing engine hits a balancing constraint. Growth
  stalls not because the engine broke, but because a constraint arrived.
* **Tragedy of the commons**: shared resource depleted by rational local use. A
  shared platform team consumed by every product team's urgent request.
* **Success to the successful**: resources flow to the currently winning unit,
  guaranteeing it keeps winning regardless of merit.
* **Escalation**: two parties respond to each other, and both lose. Two
  departments each adding approval gates to protect against the other.
* **Eroding goals**: standards quietly lowered to match performance. The
  four-hour target becomes six because six is what happens.


## How to use it in diagnosis

1. Draw the behavior over time, not the current snapshot. Get the actual graph.
2. Ask "what structure would produce that graph?"
3. Map the loops with the people in the system, on a whiteboard, out loud.
4. Look for the delay that makes people give up too early.
5. Choose leverage as high as your authority allows.


## Examples by audience

* **Health care**: emergency department crowding is not caused by slow triage.
  It is a flow problem in which discharge timing on the wards sets the ceiling
  on admission. Optimizing the front door while the back door is blocked is a
  textbook fix that fails. See [queueing theory](https://github.com/joelparkerhenderson/queueing-theory).

* **Software**: "we need more developers" against a codebase whose review and
  deployment path is the constraint is a shifting-the-burden archetype. Adding
  developers increases contention on the constraint. See
  [dora-metrics](../dora-metrics/).

* **Executive**: annual budget cycles create a reinforcing loop where units
  spend to protect next year's allocation. The behavior is rational; the rule
  produces it. Changing the rule is higher leverage than exhorting restraint.


## Limitations

* Causal loop diagrams are easy to draw and hard to validate.
* Systems language can become an excuse: "it's the system" removes agency.
  Structure explains behavior; it does not excuse conduct.
* Quantified system dynamics modeling is a specialist skill and often
  over-engineered for OD purposes.


## See also

* [sociotechnical-systems](../sociotechnical-systems/)
* [viable-system-model](../viable-system-model/)
* [cynefin-framework](../cynefin-framework/)
* Donella Meadows, *Thinking in Systems*.
* Peter Senge, *The Fifth Discipline*. See
  [learning-organization](../learning-organization/).
