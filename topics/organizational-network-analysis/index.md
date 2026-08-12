# Organizational network analysis

Organizational network analysis (ONA) maps the informal structure: who actually
goes to whom for information, advice, decisions, and trust. It reveals the
organization as it works, rather than as it is drawn.

**Evidence: Good as a method.** Social network analysis is a mature, validated
research methodology, and several of its organizational findings are robust:
brokerage positions confer information advantage, weak ties carry novel
information, and network position predicts performance and influence better than
formal rank does. The weakness is practical rather than theoretical — response
rates below roughly 70% make a map unreliable, and reported ties differ from
actual ties.

Use when: the org chart does not explain observed behavior, when planning a
change that needs informal sponsors, or when assessing what a reorganization or
a wave of departures will actually break.

Do not use when: you cannot guarantee ethical handling. ONA data is unusually
sensitive.


## What is mapped

Different questions produce different, non-overlapping networks:

* **Information**: who do you go to for the information you need to do your job?
* **Advice / expertise**: whose technical judgment do you seek?
* **Trust**: who would you tell about a mistake before it became public?
* **Energy**: who leaves you more motivated after an interaction?
* **Innovation**: who do you talk to when you have a half-formed idea?

The trust network is usually the smallest, the least like the org chart, and the
most predictive of whether a change will take hold.


## Key roles the map reveals

* **Central connectors**: high in-degree; the people everyone consults. Often
  invisible to leadership, often overloaded, and often not senior.
* **Brokers / boundary spanners**: connect otherwise separate clusters. Removing
  one disconnects parts of the organization. Rare and undervalued.
* **Peripheral nodes**: weakly connected. Sometimes new joiners; sometimes
  people quietly disengaging; sometimes deep specialists who are fine.
* **Silos**: dense internal ties, sparse external ties. Predicts handoff
  failures at the boundary. See [conways-law](../conways-law/).
* **Bottlenecks**: single points of connection whose absence stops flow.


## Methods

* **Survey-based**: ask a roster question ("name up to five people you go to for
  X"). Explicit consent, best signal quality, snapshot in time.
* **Passive / digital exhaust**: derive ties from email, chat, calendar, code
  review, or ticket data. Continuous and cheap, but ethically fraught and biased
  toward whatever tool you can read.

Prefer survey-based for OD work. Passive ONA without informed consent is
surveillance, and will be experienced as such the moment it becomes known.


## Ethics rules

* Informed consent before collection, with a genuine opt-out.
* Never report individual-level maps to managers about their reports.
* Report roles and patterns, not named rankings, unless the named person has
  agreed.
* Do not use ONA output in performance, promotion, or redundancy decisions. This
  is the single fastest way to destroy the data's validity and the
  practitioner's credibility.
* Delete raw ties on a stated schedule.

See [od-ethics](../od-ethics/).


## Examples by audience

* **Health care**: ONA reliably finds that a small number of senior nurses are
  the real information hubs of a ward, outranking the formal hierarchy. Change
  programs that recruit them succeed; programs that route only through
  consultants and managers stall.

* **Software**: code review networks are a ready-made ONA dataset. A single
  reviewer approving most changes across many repositories is a bus-factor risk
  and a delivery constraint at the same time.

* **Executive**: after an acquisition, ONA six months in shows whether the two
  organizations have actually merged. Two dense clusters with three thin links
  between them means integration exists only on paper.


## Limitations

* Snapshot; networks change quickly.
* Response rate below roughly 70% makes the map unreliable.
* Measures reported ties, which differ from actual ties.
* Tempting to over-interpret pretty diagrams.


## Questionnaire

A paired, copy-and-use diagnostic instrument for this model:
[organizational-network-analysis-questionnaire](../organizational-network-analysis-questionnaire/).


## See also

* [conways-law](../conways-law/)
* [od-ethics](../od-ethics/)
* <https://github.com/joelparkerhenderson/stakeholder-analysis>
