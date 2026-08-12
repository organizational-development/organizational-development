# Team topologies

Matthew Skelton and Manuel Pais's *Team Topologies* (2019) offers a concrete
organizational design vocabulary for knowledge work, built on
[conways-law](../conways-law/) and cognitive load.

**Evidence: Weak as a whole, good in its components.** The four-type, three-mode
scheme has not been tested. Its two foundations are much better supported:
[conways-law](../conways-law/) has direct empirical backing, and cognitive load
theory is well established in educational psychology, though its transfer to
team-level capacity is an extrapolation. Treat the vocabulary as useful and the
taxonomy as unproven.

Use when: designing team boundaries in software or any complex knowledge-work
setting, or when "everything needs coordination with everyone".

Do not use when: applying it literally outside software without translating. The
team types translate well; the terminology does not.


## Four team types

1. **Stream-aligned**: aligned to a single valuable flow of work — a product, a
   service, a customer segment, a patient pathway. The default type. Most teams
   should be this. Owns its work end to end.

2. **Enabling**: helps stream-aligned teams acquire a capability, then leaves.
   Explicitly time-boxed. Fails when it becomes a permanent consulting group.

3. **Complicated-subsystem**: owns a part requiring deep specialist knowledge —
   a pricing engine, a clinical decision algorithm, a physics model. Justified
   only when the specialism is genuinely scarce.

4. **Platform**: provides internal services that reduce cognitive load for
   stream-aligned teams. Must be consumed as a self-service product, not
   requested through a ticket queue. A platform that gatekeeps is not a
   platform; it is a bottleneck.


## Three interaction modes

1. **Collaboration**: two teams work closely for a defined period to discover
   something. High bandwidth, high cost, deliberately temporary.
2. **X-as-a-Service**: one team consumes what another provides, with minimal
   interaction. Low bandwidth, predictable, the target steady state.
3. **Facilitating**: one team helps another learn. Time-boxed.

The discipline is to name the mode explicitly for each pair of interacting
teams, and to name when it should change. Permanent collaboration is a design
failure, not a virtue.


## Cognitive load

The central constraint: a team can only hold so much. Skelton and Pais borrow
intrinsic, extraneous, and germane load. The design goal is to **minimize
extraneous load** — the accidental complexity of tooling, environments, and
process — so the team's capacity goes to the domain.

Practical test: ask a team to list everything they are responsible for. If they
cannot enumerate it, or if the list spans unrelated domains, the boundary is
wrong. Adding people does not fix an over-broad boundary; it splits attention.


## Examples by audience

* **Health care**: an integrated care team around a patient pathway is
  stream-aligned. A specialist radiology reporting unit is a
  complicated-subsystem team. An improvement or digital team that embeds for
  eight weeks and then withdraws is an enabling team; one that never withdraws
  becomes a permanent dependency and a source of resentment.

* **Software**: the canonical application. The frequent error is creating a
  "platform team" that owns shared infrastructure but operates as a ticket
  queue, converting X-as-a-Service into permanent Collaboration and adding
  latency to every stream-aligned team.

* **Executive**: use the four types as a language for portfolio-level design.
  Ask of every team: which type is it, and who decided? Teams with no clear type
  usually have no clear owner either.


## Limitations

* Software-shaped assumptions; product-aligned flow is not always available.
* Risk of ritual adoption — renaming existing teams without changing boundaries,
  ownership, or interaction modes.
* Says little about hierarchy, reward, or career, which
  [galbraith-star-model](../galbraith-star-model/) covers.


## Questionnaire

A paired, copy-and-use diagnostic instrument for this model:
[team-topologies-questionnaire](../team-topologies-questionnaire/).


## See also

* [conways-law](../conways-law/)
* [sociotechnical-systems](../sociotechnical-systems/)
* [dora-metrics](../dora-metrics/)
* <https://teamtopologies.com>
