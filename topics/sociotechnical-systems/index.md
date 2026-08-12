# Sociotechnical systems

Sociotechnical systems (STS) theory came out of the Tavistock Institute in the
1950s, from Eric Trist and Ken Bamforth's study of British coal mines. A new
mechanized "longwall" method raised technical efficiency but destroyed the small
self-managing teams the old method depended on, and productivity fell.

The finding: the social system and the technical system must be designed
together. Optimizing either alone degrades the whole. This is called **joint
optimization**.

**Evidence: Moderate to good.** The original coal mining studies were
case-based, but the core claim has accumulated wide support: technology
implementations that ignore social arrangements underperform, and this is one of
the most consistent findings in the information systems and health informatics
literature. The work design principles overlap with the strongly supported
[job-characteristics-model](../job-characteristics-model/).

Use when: introducing new technology, redesigning work, or explaining why a
technically excellent system produced worse outcomes.

Do not use when: the change is purely social with no technical component, though
this is rarer than it looks.


## Core principles

* **Joint optimization**: design the social and technical together, or lose.
* **Minimal critical specification**: specify no more than necessary; leave the
  people doing the work to determine the rest.
* **Variance control at source**: handle problems where they arise, not by
  escalating them up a hierarchy.
* **Multifunctional workers**: redundancy of function beats redundancy of parts;
  cross-skilled people absorb variance that spare capacity cannot.
* **Boundary location**: draw team boundaries around whole tasks, so a team can
  complete something meaningful without handoff.
* **Incompletion**: design is never finished; the system keeps changing.


## Why it matters now

Every modern digital transformation is a sociotechnical intervention whether or
not it is framed as one. Electronic health records, CI/CD pipelines, workflow
tools, and now AI assistants all reallocate authority, attention, and status
along with tasks. Deployments that treat this as a training problem fail
predictably.


## Examples by audience

* **Health care**: electronic health record rollouts are the canonical modern
  case. The technical system improves data capture; the social system loses the
  hallway handover, the nurse's marginal note, and the physician's eye contact
  with the patient. Documented consequences include burnout and new error modes.
  Joint design means clinicians shaping the workflow, not being trained on it.

* **Software**: a new deployment platform that centralizes control raises
  technical consistency and lowers team autonomy. If teams previously absorbed
  variance locally, the central team becomes a queue. See
  [team-topologies](../team-topologies/), [conways-law](../conways-law/).

* **Executive**: enterprise resource planning and shared service centers are
  sociotechnical decisions presented as cost decisions. The social cost — loss
  of local variance control — usually appears two years later as "we've become
  bureaucratic".


## Applying it

1. Map the technical system: tools, flows, artifacts, automation.
2. Map the social system: roles, teams, authority, informal networks, identity.
3. Find where the technical design assumes a social arrangement that does not
   exist, or destroys one that is load-bearing.
4. Redesign both together, with the people who do the work.
5. Give teams whole tasks and the authority to handle their own variance.


## Limitations

* Slower and more participative than a technology-led rollout, which is exactly
  why it gets skipped under deadline pressure.
* Hard to evidence in advance; its strongest evidence is post-mortem.


## See also

* [systems-thinking](../systems-thinking/)
* [job-characteristics-model](../job-characteristics-model/)
* [team-topologies](../team-topologies/)
* Trist & Bamforth (1951); Cherns, "The Principles of Sociotechnical Design".
