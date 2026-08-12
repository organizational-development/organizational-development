# Plan-Do-Study-Act and the Model for Improvement

PDSA is the improvement cycle from Walter Shewhart and W. Edwards Deming. Deming
insisted on **Study** rather than the older "Check", because the point is to
learn from the comparison of prediction to result, not merely to inspect.

The **Model for Improvement** (Associates in Process Improvement; popularized by
the Institute for Healthcare Improvement) wraps PDSA in three questions asked
first.

**Evidence: Mixed.** The underlying components are sound: statistical process
control is well founded, and explicit prediction before observation is basic
scientific method. The applied literature is poor — systematic reviews of
published health care PDSA work find that most reports omit predictions, run a
single cycle, use no time-series data, and do not meet the method's own
criteria. The method is better than most of its practice.

Use when: improving a process incrementally with the people who run it, in short
cycles.

Do not use when: the problem is strategic, structural, or requires a decision
rather than an experiment.


## The three questions

1. **What are we trying to accomplish?** A specific, measurable, time-bound aim.
   "Reduce door-to-antibiotic time for suspected sepsis from 90 to 45 minutes by
   December."
2. **How will we know that a change is an improvement?** The measures, agreed in
   advance — outcome, process, and balancing.
3. **What changes can we make that will result in improvement?** Change ideas,
   drawn from theory, from bright spots, or from the people doing the work.


## The cycle

* **Plan**: state the change, who does what, where, when — and **predict the
  result**. The prediction is mandatory; without it, Study degenerates into
  rationalization.
* **Do**: run it at small scale. Record what actually happened, including the
  things that went wrong and the departures from plan.
* **Study**: compare result to prediction. Where they differ, ask why. The
  learning is in the difference.
* **Act**: adopt, adapt, or abandon. Then start the next cycle.


## Scale of testing

The most common error is testing too big. Ramp deliberately:

* One clinician, one patient, one shift.
* One clinician, five patients.
* Three clinicians, one week.
* One ward, one month.
* Spread.

Move up a level only after a successful cycle. "Test of change with one patient
tomorrow" gets agreement that "pilot across the directorate" never will.


## Three kinds of measure

* **Outcome**: did the thing we care about improve?
* **Process**: is the change actually happening? (Usually the first thing to
  check when the outcome does not move.)
* **Balancing**: what got worse elsewhere? Non-negotiable. Every improvement in
  one place can export harm to another.


## Run charts and special cause

Plot data over time, not before-and-after bars. Before/after comparison cannot
distinguish improvement from normal variation, and it is how most improvement
claims are inflated. Learn the basic run chart rules — shift, trend, runs,
astronomical point — before claiming an effect. See
[measurement-and-metrics](../measurement-and-metrics/).


## Examples by audience

* **Health care**: PDSA is the lingua franca of clinical improvement. Its most
  common failure is ritual PDSA: the paperwork is completed, no prediction is
  recorded, the cycle is run once, and it is called a project. A real PDSA is
  fast, small, repeated, and often uncomfortable.

* **Software**: the same logic as a hypothesis-driven experiment. "We believe
  reducing review batch size will cut lead time; we predict a 30% reduction in
  four weeks; if not, we will conclude the constraint is elsewhere." Attach the
  prediction to the ticket.

* **Executive**: ask any improvement program for its predictions, recorded
  before the change. Programs that only report post-hoc successes are not
  learning; they are marketing.


## Limitations

* Weak for problems requiring redesign rather than iteration.
* Published PDSA work in health care is frequently of poor quality — single
  cycles, no predictions, no measures.
* Small-scale testing does not always predict at-scale behavior.


## See also

* [improvement-kata](../improvement-kata/)
* [action-research](../action-research/)
* [measurement-and-metrics](../measurement-and-metrics/)
* <https://www.ihi.org>
