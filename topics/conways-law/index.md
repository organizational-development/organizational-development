# Conway's law

Melvin Conway, 1967: "Organizations which design systems are constrained to
produce designs which are copies of the communication structures of these
organizations."

The system you build will mirror how your teams talk to each other. This is one
of the few genuinely predictive statements in organizational design, and it has
empirical support from later studies of software architecture and code
ownership.

**Evidence: Good.** Unusually well supported for an organizational claim. The
mirroring hypothesis — that product architecture reflects organizational
communication structure — has been tested empirically across commercial and open
source codebases and generally confirmed. What is less established is the
prescriptive half: that deliberately reorganizing to fit a target architecture
reliably produces it.

Use when: designing teams, planning an architecture change, or explaining why a
technical boundary keeps being violated.

Do not use when: treating it as fatalism. The law is a constraint to exploit,
not a sentence.


## The inverse Conway maneuver

If structure determines architecture, then choosing the architecture you want
and organizing teams to match will tend to produce it. This is the standard
modern application: design the team boundaries as deliberately as the module
boundaries.

Corollary: a reorganization is an architecture decision, whether or not anyone
in the room knows it.


## Signals that Conway's law is operating

* A module that no team owns, and that everyone edits reluctantly.
* An API whose shape matches a reporting line rather than a domain.
* A "coordination layer" whose only purpose is to bridge two org units.
* Integration bugs concentrated exactly at team boundaries.
* Documentation that describes the org chart when asked about the system.


## Examples by audience

The law is stated about systems design, but the mechanism — communication
structure constrains output structure — generalizes to any designed artifact.

* **Health care**: a patient pathway that crosses four departments produces four
  records, four handovers, and four opportunities for information loss. The
  pathway mirrors the departments, not the patient. Integrated care teams are an
  inverse Conway maneuver on clinical services.

* **Software**: microservice boundaries that do not match team boundaries create
  either constant cross-team coordination or de facto shared ownership. See
  [team-topologies](../team-topologies/).

* **Executive**: a product that customers experience as fragmented is usually a
  product built by units that do not talk. Fixing the customer experience by
  adding a "customer experience" function adds a fifth silo.


## How to use it

1. Draw the actual communication structure — who really talks to whom, weekly.
   Not the org chart. See
   [organizational-network-analysis](../organizational-network-analysis/).
2. Draw the target system boundaries.
3. Where they disagree, decide which one to move. Moving the org is usually
   slower but more durable than fighting the mismatch forever.
4. Reduce the number of boundaries that require high-bandwidth coordination.


## Limitations

* Descriptive strength is high; prescriptive precision is low. It tells you a
  mismatch will hurt, not exactly how to organize.
* Reorganizing to fit an architecture imposes real human cost; do not do it
  casually or repeatedly.


## See also

* [team-topologies](../team-topologies/)
* [sociotechnical-systems](../sociotechnical-systems/)
* [galbraith-star-model](../galbraith-star-model/)
* Conway, "How Do Committees Invent?" (1968).
