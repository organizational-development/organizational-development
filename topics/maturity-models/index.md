# Maturity Models

A maturity model is a business tool used to assess people/culture,
processes/structures, and objects/technology.

See https://en.wikipedia.org/wiki/Maturity_model

**Evidence: Weak.** Maturity models are descriptive conventions, not tested
theories. Progression through levels has rarely been shown to predict outcomes,
the level definitions are usually authored by advocates or vendors, and the
assumption that a single linear path runs from worse to better is an assertion
rather than a finding. Evidence for CMMI specifically is contested and largely
drawn from studies with selection problems. The rebuttals listed in this file
are worth taking seriously. What maturity models do well is give a group shared
vocabulary for a capability conversation; they fail when treated as a scorecard
tied to funding or used to compare units with different constraints.

Use when: you need shared vocabulary for a capability conversation and a
direction of travel; when building a career framework or a capability roadmap.

Do not use when: the level becomes the goal, or when scores carry funding,
headcount, or reputational consequences. Consequential scoring produces
compliance behavior rather than capability, and the data stops being worth
collecting. For delivery capability specifically, prefer outcome measures such
as [dora-metrics](../dora-metrics/) over practice conformance.


## Maturity model levels

Maturity model levels are typically a series of steps of sophistication such as:

- Level 0: Not Applicable
- Level 1: Initiate
- Level 2: Develop
- Level 3: Standardize
- Level 4: Manage
- Level 5: Orchestrate

Maturity model levels have a range of terminology in various industries such as:

- Level 0: None, Never, Negligible, Not Applicable.
- Level 1: Initiate, Investigate, Implicit, Individual-oriented, Informal-usage.
- Level 2: Develop, Describe, Duplicate, Direct-oriented, Department-usage.
- Level 3: Standardize, Specify, Scale, Service-oriented, Segment-usage
- Level 4: Manage, Measure, Mainstream, Mission-oriented, Mass-usage.
- Level 5: Orchestrate, Optimize, Originate, Opportunity-oriented, Outsize-usage

### Who decides what goes into a maturity model?

The team that creates the maturity model decides what goes into it. For creating
your own maturity models, we suggest using a "decision record" that can help
your team research what you want to go in, and document your choices, in order
to help other people understand and leverage your work.

### Is a maturity model a snapshot in time or a future plan?

Snapshot. Good teams will leverage the snapshot in order to create future plans,
such as plans to work toward a higher maturity model level.

### Is a maturity model descriptive or prescriptive?

Descriptive. A maturity model describes the levels and their items, and does not
prescribe how a team moves from one level to the next, or acquires items. In
rare cases, a specific maturity model may provide adjuct advice, yet this is
inherent to the maturity model.

### Can a maturity model evolve over time?

Yes. As an organization evolves, each of its maturity models can evolve. For
example, some organizations like to look ove each of their maturity models, each
year, to ensure that each maturity model is still useful, and also to update
each model as desired, based n the organization's goals and capabilities.

### Does a maturity model have an end state?

Yes. Then end state of a maturity model is when it is no longer useful to a
team. For example, this can happen when a team decides that its current
capabilties are fine as is, or when a team outgrows a maturity model by
acheiving its highest level then wanting to improve even more.

### Is a maturity model different than a scientific model?

Yes. A maturity model is intended to be a quick easy summary in order to help a
team communicate about its current capabilties, and plan for future capabilties.
The word "model" has the meaning "a small thing that represents another thing,
that is often larger, or more complex, or more abstract." For comparison a
"scientific model" is intended to explain and predict the behaviour of a real
object or system, such as a visualization model that can contextualize a
scientific object, or a predictive model that can foreccast a scientific system.

### Is a maturity models verifiable?

Yes. A maturity model can describe its levels and items in terms of qualitative
metrics and/or quantitative metrics. For example, a programmer can describe
Level 1 "Initiate" in terms of "Write a program that prints Hello World", up to
Level 5 "Orchestrate" in terms of "Run a worldwide distributed system in concert
with our key partners".


## Examples by audience

* **Health care**: clinical competency frameworks and improvement maturity
  assessments are pervasive, and the risk is level-chasing for accreditation
  rather than capability. A ward that scores level 4 on documented process and
  level 1 on measurement is being run on faith, and the accreditation will not
  say so.

* **Software**: engineering maturity models are useful for identifying missing
  practices and dangerous for ranking teams, because teams face genuinely
  different constraints — regulated systems, embedded hardware, legacy
  platforms. For delivery capability specifically, prefer outcome measures. See
  [dora-metrics](../dora-metrics/), which measures what a team achieves rather
  than which practices it conforms to.

* **Executive**: use maturity models to allocate investment across a portfolio,
  and never to compare units. The moment a low score costs a unit money or
  headcount, you are measuring reporting behavior rather than capability, and
  the data stops being worth collecting.


## Limitations

* Descriptive, not prescriptive: a maturity model describes levels and does not
  tell a team how to move between them.
* Level progression rarely predicts outcomes, so a higher level is evidence of
  conformance rather than of effectiveness.
* Usually authored by advocates or vendors whose product moves you up the
  levels.
* Assumes a single linear path from worse to better, which is an assertion
  rather than a finding. See the rebuttals above.


## Questionnaire

A paired, copy-and-use diagnostic instrument for this model:
[maturity-models-questionnaire](../maturity-models-questionnaire/).
