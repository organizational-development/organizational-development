# After action review

The after action review (AAR) is a structured debrief developed by the US Army
and now standard across health care, emergency services, and software
operations. It is the cheapest organizational learning mechanism available, and
the one most often degraded into a status report.

**Evidence: Good.** One of the better-evidenced interventions in this
collection. Meta-analyses of structured team debriefs find substantial and
consistent improvements in team performance, on the order of a 20 to 25 percent
improvement over teams that do not debrief, across military, medical, and
aviation settings. The effect depends on the conditions described here —
blameless framing, facilitation, participation regardless of rank, and
follow-through — and an AAR that degrades into a status report should not be
expected to produce it.

Use when: after any significant event — an incident, a launch, a project phase,
a difficult clinic, a failed bid. Successes deserve AARs as much as failures.

Do not use when: it will be used to allocate blame. A blame-adjacent AAR
produces false data and teaches people to say nothing next time.


## The four questions

1. **What was supposed to happen?**
2. **What actually happened?**
3. **Why were there differences?**
4. **What will we do differently next time?**

That is the entire method. Its power is in the discipline: establishing the
intent *before* discussing the outcome prevents hindsight from rewriting what
people meant to do.


## Ground rules

* **No blame.** Focus on the system and the decisions, not the individuals. See
  [just-culture](../just-culture/).
* **Everyone participates**, and rank is left outside. In the Army version, a
  private may contradict a colonel; that is the point.
* **Facilitated, not chaired**, and preferably not by the person who led the
  event.
* **Soon after the event**, while memory is fresh — hours to days, not weeks.
* **Focused on learning**, not on producing a document.
* **Findings are recorded and shared**, or the learning stays in the room.


## Facilitation guidance

* Ask the most junior people first; seniority anchors the account otherwise.
* Establish the timeline factually before discussing causes. Disagreement about
  what happened is common and informative.
* Ask "what made that the reasonable thing to do at the time?" rather than "why
  did you do that?" The first invites explanation; the second invites defense.
* Beware hindsight bias: with the outcome known, the correct action looks
  obvious to everyone. It was not obvious then, and reconstructing what was
  actually knowable at the time is the core analytical work.
* Distinguish **counterfactuals** ("they should have noticed the alarm") from
  **causes** ("the alarm was one of forty active, and eleven were routine").
  Counterfactuals feel like findings and are not.
* End with named owners and dates, or accept that nothing will change.


## Variants

* **Incident postmortem / blameless postmortem**: the software operations
  lineage. Adds a detailed timeline, contributing factors, and action items with
  owners. See <https://github.com/joelparkerhenderson/issue-postmortem-template>.
* **Hot wash**: immediate, brief, on-site, within minutes of the event ending.
* **Morbidity and mortality (M&M) conference**: the clinical lineage. Older than
  the AAR, and its quality varies enormously with how blame-free it actually is.
* **Retrospective**: the agile lineage, run on a cadence rather than after an
  event. See <https://github.com/joelparkerhenderson/agile-checklist>.
* **Pre-mortem**: run *before* the event. "It is a year from now and this failed
  completely. Write down why." Surfaces risks that people will not raise as
  objections but will happily raise as fiction.


## Why AARs decay

Predictable failure modes, all recoverable:

* The senior person speaks first and everyone calibrates to their account.
* It becomes a status report or a defense of decisions already made.
* Actions are recorded and never done, so participants stop investing.
* Only failures are reviewed, so the process becomes associated with blame.
* The same findings recur for years, unaddressed, which is itself the most
  important finding and is never named.

Countermeasure: audit your last ten AARs for repeated findings. Repetition means
the mechanism is producing documents, not change.


## Examples by audience

* **Health care**: a debrief after a cardiac arrest call, run for five minutes
  in the corridor, is a hot wash and is standard good practice in many units.
  The full AAR for a serious incident must be separated in time and personnel
  from any disciplinary process, and everyone must be told which one they are
  in.

* **Software**: blameless post-incident review is the mature default. The single
  highest-value practice is publishing them internally in full — including the
  embarrassing parts — so that teams learn from incidents they did not
  experience.

* **Executive**: executive teams almost never run AARs on their own decisions.
  Reviewing a major decision twelve months later against what was predicted at
  the time is uncomfortable, cheap, and the fastest available route to better
  executive judgment. See
  <https://github.com/joelparkerhenderson/decision-record>.


## See also

* [just-culture](../just-culture/)
* [learning-organization](../learning-organization/)
* [high-reliability-organizations](../high-reliability-organizations/)
