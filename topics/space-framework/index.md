# SPACE framework

The SPACE framework, from Nicole Forsgren, Margaret-Anne Storey, Chandra
Maddila, Thomas Zimmermann, Brian Houck, and Jenna Butler, is a framework for
measuring developer productivity across five dimensions. It exists specifically
to counter single-metric productivity measurement.

Its central rule: **pick metrics from at least three of the five dimensions, and
include at least one perceptual measure.** No single number describes
productivity.

**Evidence: Moderate as a principle, weak as an instrument.** There is no
validated SPACE instrument and no prescribed metric set, so it cannot be
benchmarked the way [dora-metrics](../dora-metrics/) can. The claim it rests on
is well supported: single-metric productivity measurement produces distortion,
and activity counts do not track outcomes. Its authors' central warning against
individual-level measurement is consistent with the wider evidence on metric
gaming.

Use when: measuring knowledge-worker productivity without reducing it to output
counting; countering a request for "a developer productivity metric".

Do not use when: measuring individuals for performance management. The authors
explicitly warn against this.


## The five dimensions

1. **Satisfaction and wellbeing** — how fulfilled people are with their work,
   team, tools, and culture; and burnout. Included first deliberately:
   satisfaction predicts retention and future productivity, so a productivity
   gain purchased by burning people is a loss on a delay.

2. **Performance** — the outcome of the work. Quality, reliability, customer
   satisfaction, business impact. Hard to attribute to individuals, which is the
   point.

3. **Activity** — counts of actions: commits, pull requests, deployments,
   documents, tickets closed. The easiest to collect and the most misleading in
   isolation. Activity is not productivity.

4. **Communication and collaboration** — discoverability of information, review
   quality, onboarding time, network connectedness, how work flows between
   people. See
   [organizational-network-analysis](../organizational-network-analysis/).

5. **Efficiency and flow** — the ability to do work with minimal interruption or
   delay. Handoffs, wait time, interruption frequency, uninterrupted focus time,
   perceived flow.


## The three levels

Each dimension can be measured at individual, team, or system level. The authors
recommend team and system, and warn that individual-level measurement changes
behavior toward the metric.

| Level | Appropriate use |
| --- | --- |
| Individual | Personal reflection only, chosen by the person, never reported upward |
| Team | The primary unit for improvement work |
| System | End-to-end flow across teams; where the largest constraints live |


## Example metric set

A workable set drawing on three dimensions plus a perceptual measure:

| Dimension | Metric | Source |
| --- | --- | --- |
| Satisfaction | Developer satisfaction score; burnout item | Quarterly survey |
| Efficiency and flow | Lead time; uninterrupted focus hours per week | Pipeline; calendar |
| Communication | Pull request review latency; time to first response | Version control |
| Performance | Change failure rate | Incident data |
| Activity | Deployment frequency | Pipeline |

Note the balance: if flow improves while satisfaction falls, the gain is being
paid for out of people.


## Examples by audience

The dimensions generalize directly to other knowledge work.

* **Health care**: Activity is clinic throughput and procedures performed —
  routinely used alone, which is the classic error. SPACE-style balance would
  add clinician satisfaction and burnout, patient outcomes (Performance), MDT
  and referral responsiveness (Communication), and administrative interruption
  burden (Efficiency and flow). Health systems measure activity extensively and
  flow-interruption almost never, which is one reason clinician frustration is
  invisible in management data.

* **Software**: the native domain. The most common institutional failure is a
  leadership request for "lines of code" or "story points per engineer" — a pure
  Activity metric at the individual level, which is the exact combination the
  framework exists to refuse.

* **Executive**: when asked for a single productivity number, offer a set of
  three to five spanning the dimensions instead, and explain that the single
  number will be optimized against. This conversation is worth having once,
  properly, rather than repeatedly.


## Limitations

* No prescribed metric set, which makes it harder to adopt and harder to
  benchmark than [dora-metrics](../dora-metrics/).
* Perceptual measures require regular surveying and survey fatigue is real.
* Does not solve attribution: system-level improvements cannot be assigned to
  contributors, and someone will always want them to be.


## See also

* [dora-metrics](../dora-metrics/)
* [measurement-and-metrics](../measurement-and-metrics/)
* [job-characteristics-model](../job-characteristics-model/)
* Forsgren et al., "The SPACE of Developer Productivity", *ACM Queue* (2021).
