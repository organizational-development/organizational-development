# Theory of change

A theory of change is an explicit, testable causal chain from what you do to the
outcome you want, with the assumptions named. It originated in program
evaluation and international development, and it is the most rigorous way to
state what an OD program is actually claiming.

**Evidence: Not a model — an evaluation method.** Widely required by funders and
evaluators, and there is limited direct evidence that producing one improves
program outcomes. Its defensible claim is narrower and does not need a trial: an
intervention whose assumptions are written down in advance can be falsified, and
one whose assumptions are not written down will be evaluated retrospectively
against whatever happened. The discipline is the deliverable.

Use when: launching any program you will later be asked to justify; when
stakeholders disagree about what a program is for; when you want the program to
be falsifiable.

Do not use when: the work is genuinely exploratory and premature specification
would foreclose learning. Even then, state the hypothesis.


## The chain

```
Inputs → Activities → Outputs → Outcomes → Impact
```

* **Inputs**: money, people, time, tooling.
* **Activities**: what you do — workshops, coaching, redesign, tooling changes.
* **Outputs**: countable products of activities — sessions delivered, people
  trained, process documented. **Not evidence of success.**
* **Outcomes**: changes in behavior, capability, or condition. Short, medium,
  long term.
* **Impact**: the ultimate goal — patient outcomes, delivery performance,
  retention, mission achievement.

The discipline that matters: **between each pair of boxes there is an
assumption**, and the assumption is where programs fail. Write the assumptions
down. They are the falsifiable content.

See <https://github.com/joelparkerhenderson/outputs-vs-outcomes>.


## Building one backwards

Always work right to left.

1. State the **impact** you want, in measurable terms.
2. Ask: what **outcomes** must occur for that impact to follow? What must be
   true about behavior?
3. Ask: what **outputs** would produce those outcomes?
4. Ask: what **activities** produce those outputs?
5. Ask: what **inputs** do the activities require?
6. For every arrow, write the assumption, and rate your confidence in it.
7. For every low-confidence assumption, decide how you would test it early and
   cheaply.


## Worked example: psychological safety program

| Stage | Content |
| --- | --- |
| Inputs | Facilitator time, 2 hours per team per month, exec sponsorship |
| Activities | Leader behavior coaching; team retrospectives; blameless incident reviews |
| Outputs | 12 leaders coached; 40 retrospectives held; 15 blameless reviews |
| Outcomes (short) | Staff report they can raise concerns without fear |
| Outcomes (medium) | Incident and near-miss reporting rate rises |
| Outcomes (long) | Problems surface earlier; fewer escalate |
| Impact | Fewer serious harm events; lower turnover |

Assumptions, each stated explicitly:

* Leaders can change behavior with coaching alone. *(Low confidence — test.)*
* Reported safety translates to actual speaking-up behavior. *(Medium.)*
* Higher reporting reflects better reporting, not more incidents. *(Critical:
  this metric moves the wrong way if misread. Pre-agree the interpretation with
  leadership before the data arrives.)*
* Earlier surfacing reduces harm rather than merely relocating it. *(Medium.)*

The third assumption is the kind that sinks programs. A rising reporting rate is
success, and will be presented by someone as failure. Agree in advance.


## Examples by audience

* **Health care**: mandatory in most grant and improvement funding, and
  routinely produced as compliance paperwork rather than used. Its real value is
  forcing agreement on whether a rising metric is good or bad *before* it rises.

* **Software**: a developer experience program whose theory of change stops at
  outputs ("we shipped a new CI system") cannot answer whether it helped. Chain
  it to lead time, change failure rate, and retention. See
  [dora-metrics](../dora-metrics/).

* **Executive**: ask for the theory of change behind any major program before
  approving it, and specifically for the assumptions list. A program that cannot
  name its assumptions has not been thought through.


## Limitations

* Can become an elaborate document that is written once and never revisited.
* Implies more linearity than complex systems allow; in the Complex domain treat
  it as a hypothesis to be revised, not a plan. See
  [cynefin-framework](../cynefin-framework/).
* Vulnerable to reverse-engineering: writing the theory to justify an
  intervention already chosen.


## See also

* [measurement-and-metrics](../measurement-and-metrics/)
* [evidence-based-practice](../evidence-based-practice/)
* <https://github.com/joelparkerhenderson/objectives-and-key-results>
