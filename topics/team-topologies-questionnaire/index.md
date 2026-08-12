# Team Topologies Questionnaire

To assess team design using team topologies, use this questionnaire. Part A
classifies a single team and checks whether its boundary is sound, scoring 1
(badly wrong) to 5 (clean). Part B assesses the interactions between teams.

Run Part A once per team, then Part B across the set. Assessing one team in
isolation misses the point, because most team design problems live at the
boundaries.

See [team-topologies](../team-topologies/).

**Evidence: Weak as a whole, good in its components.** The four-type, three-mode
scheme is untested. Its foundations — [conways-law](../conways-law/) and
cognitive load — are much better supported.


## Part A: Assess one team

Team name: ____________________________________________________


### A1. Type

- Question: Which type is this team intended to be?
  - [ ] Stream-aligned — owns a flow of work end to end
  - [ ] Enabling — builds capability in others, then leaves
  - [ ] Complicated-subsystem — owns a part needing deep specialism
  - [ ] Platform — provides self-service capability to other teams
  - [ ] Nobody has decided

- Question: Would the team members give the same answer as leadership?
  - Rating (1–5): [ ]

- Question: If Enabling: is there a stated end date, and is it real?
  - Rating (1–5): [ ]

- Question: If Platform: is it consumed self-service, or through a request
  queue? (Score 5 for genuine self-service.)
  - Rating (1–5): [ ]

- Question: If Complicated-subsystem: is the specialism genuinely scarce, or is
  this a historical accident?
  - Rating (1–5): [ ]


### A2. Boundary

- Question: Can the team enumerate everything it is responsible for, without
  hesitating or arguing?
  - Rating (1–5): [ ]

- Question: Does that list span one coherent domain, or several unrelated ones?
  - Rating (1–5): [ ]

- Question: Can the team deliver something valuable end to end without waiting
  on another team?
  - Rating (1–5): [ ]

- Question: Is there work in the team's domain that no team owns?
  - Rating (1–5, where 5 = no orphaned work): [ ]


### A3. Cognitive load

- Question: How many distinct domains, systems, or technologies must a team
  member hold in their head to be effective? (Score 5 for a manageable number.)
  - Rating (1–5): [ ]

- Question: How much of the team's capacity goes to extraneous load —
  environments, tooling friction, process overhead, access requests — rather
  than to the domain?
  - Rating (1–5, where 5 = very little): [ ]

- Question: When the team is overloaded, is the proposed remedy usually "add
  people" rather than "narrow the boundary"?
  - Rating (1–5, where 5 = we narrow the boundary): [ ]


### A4. Flow

- Question: Does the team have the autonomy — access, permissions, deployment
  rights, decision rights — that its type implies?
  - Rating (1–5): [ ]

- Question: Does the team get feedback from the real world about the work it
  does?
  - Rating (1–5): [ ]


## Part B: Assess the interactions

For every pair of teams that interact regularly, complete one row.

| Team A | Team B | Intended mode | Actual mode | Since when | Should change to | Rating (1–5) |
| --- | --- | --- | --- | --- | --- | --- |
| | | | | | | [ ] |
| | | | | | | [ ] |
| | | | | | | [ ] |
| | | | | | | [ ] |

Modes: **Collaboration** (high bandwidth, temporary, for discovery),
**X-as-a-Service** (low bandwidth, the target steady state), **Facilitating**
(time-boxed helping).

Then score:

- Question: For how many pairs has anyone explicitly named the intended mode?
  - Rating (1–5): [ ]

- Question: How many pairs are in permanent Collaboration — high-bandwidth
  coordination with no end date? (Score 5 for none.)
  - Rating (1–5): [ ]

- Question: How many teams must be involved to release a typical change? (Score
  5 for one.)
  - Rating (1–5): [ ]

- Question: Do team boundaries match the boundaries of the systems, services, or
  pathways we actually want?
  - Rating (1–5): [ ]


## Part C: Analysis

* **"Nobody has decided" on A1 is the most common and most consequential
  finding.** A team with no agreed type usually has no clear owner, no clear
  boundary, and an ever-growing remit. Decide the type before anything else.

* **A low A2 enumeration score means the boundary is wrong**, not that the team
  needs more people. Adding people to an over-broad boundary splits attention
  and makes it worse. Narrow the remit instead.

* **Permanent Collaboration is a design failure, not a virtue.** Two teams in
  high-bandwidth coordination indefinitely should either merge, or one should
  turn what the other needs into a service. Name a date by which the mode
  changes.

* **A Platform team consumed through a ticket queue is not a platform.** It has
  become a bottleneck and has converted X-as-a-Service into permanent
  Collaboration, adding latency to every team it serves. This is the single most
  common misapplication of the model.

* **An Enabling team with no end date has become a permanent dependency**, and
  usually a resented one. Set the date, and hold it.

* **Low B "teams per release" scores are the flow constraint.** Every additional
  team in the path multiplies coordination cost and wait time. This is usually
  the highest-leverage thing on the sheet. See [dora-metrics](../dora-metrics/).

* **If boundaries do not match desired system boundaries, decide which one
  moves.** Conway's law will resolve the mismatch for you if you do not, and it
  will resolve it in favor of the org chart.

* **Beware ritual adoption.** Renaming existing teams to the four types without
  changing boundaries, ownership, or interaction modes changes nothing and makes
  the vocabulary useless for the next attempt.
