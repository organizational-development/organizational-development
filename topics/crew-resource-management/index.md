# Crew resource management

Crew resource management (CRM) is a team training approach developed by aviation
after a series of accidents in which technically airworthy aircraft crashed
because of communication and authority failures on the flight deck. It has been
widely adapted into health care, and it is directly applicable to any
high-consequence knowledge work.

The originating insight: the accidents were not caused by lack of technical
skill. They were caused by junior crew being unable to effectively challenge a
captain who was wrong.

**Evidence: Good in aviation, moderate to good in health care.** Among the
better-evidenced interventions here. Aviation adoption coincided with sustained
accident reduction, though confounded by many simultaneous safety improvements.
In health care, systematic reviews of team training find consistent improvements
in teamwork behaviors and knowledge, and improvements in clinical outcomes in
several large studies, with substantial heterogeneity. Programs that work share
features: multidisciplinary, simulation-based, with leadership participation and
sustained reinforcement. One-off e-learning does not work.

Use when: hierarchy suppresses safety-critical information; when handovers fail;
when "someone knew but didn't say" appears in an incident report.

Do not use when: the failure is genuinely technical.


## Core components

* **Flattened authority gradient**: seniority is preserved for decisions, and
  suspended for information. Anyone may state a concern; the senior person still
  decides.
* **Assertion protocols**: a scripted escalation ladder so that challenging is a
  procedure rather than an act of courage.
* **Closed-loop communication**: instruction, read-back, confirmation. Removes
  the assumption that being spoken to is being heard.
* **Briefing and debriefing**: shared mental model established before the task,
  and reviewed after. See [after-action-review](../after-action-review/).
* **Standardized handover**: a fixed structure so nothing depends on memory or
  on rapport.
* **Situational awareness and cross-monitoring**: everyone watches the whole
  situation, not only their own task, and is expected to say what they see.
* **Explicit workload management**: naming overload as a condition to be
  declared, not a weakness to be hidden.


## Graded assertiveness

The most transferable tool. A scripted ladder, escalating only as needed:

1. **Probe** — "I'm not sure that's right; can you help me understand?"
2. **Alert** — "I'm concerned about the dose."
3. **Challenge** — "I need you to stop and re-check the dose."
4. **Emergency** — "Stop. I am not going to continue."

A common health care variant is **PACE**: Probe, Alert, Challenge, Emergency.
Another is **CUS**: "I'm **C**oncerned. I'm **U**ncomfortable. This is a
**S**afety issue."

Why scripting works: it converts an interpersonal risk into a professional
routine. The junior person does not have to invent the words or judge whether
the moment warrants confrontation — the protocol has already decided. This makes
it effective even where the underlying culture has not yet changed, which is
what distinguishes it from culture-first approaches.


## Structured handover formats

* **SBAR**: Situation, Background, Assessment, Recommendation. Used widely in
  health care; equally usable for an engineering escalation or an executive
  briefing.
* **I-PASS**: Illness severity, Patient summary, Action list, Situation
  awareness and contingency planning, Synthesis by receiver. The final synthesis
  step — the receiver reads back — is the part that carries most of the benefit,
  and the part most often dropped.


## Evidence

Reasonably strong in aviation. In health care the picture is mixed but positive:
simulation-based team training programs show improvements in teamwork behaviors
and, in several large studies, in clinical outcomes. The programs that work
share features: multidisciplinary, in situ or high-fidelity simulation,
leadership participation, and sustained reinforcement rather than a single
training day.

Programs that fail are typically a one-off e-learning module with no simulation
and no senior participation.


## Examples by audience

* **Health care**: the WHO surgical safety checklist is CRM applied — it
  includes a designated point where everyone in theatre states their name and
  role, which measurably increases the likelihood that a junior speaks up later.
  Checklists that are read out by one person without pause do not produce this
  effect.

* **Software**: incident command practice is CRM for operations. A declared
  incident commander, explicit role assignment, closed-loop communication for
  every action taken in production, and a structured handover between shifts of
  responders.

* **Executive**: board and executive meetings have severe authority gradients
  and no assertion protocol. Adopting one — a designated challenger role, a
  round-robin before the senior person speaks, a required dissent record in the
  minutes — is a cheap, high-yield intervention. See
  <https://github.com/joelparkerhenderson/decision-record>.


## Limitations

* Training decays without reinforcement; annual refreshers are minimal.
* Cannot survive a senior person who punishes a challenge. One such incident
  teaches the whole department that the protocol is decorative.
* Adaptation from aviation to health care and software needs care: the tasks
  differ in tempo, reversibility, and team stability.


## See also

* [psychological-safety](../psychological-safety/)
* [just-culture](../just-culture/)
* [high-reliability-organizations](../high-reliability-organizations/)
* [hofstede-cultural-dimensions](../hofstede-cultural-dimensions/) — why graded
  assertiveness matters most where the power distance gradient is steepest.
