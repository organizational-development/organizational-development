# Just culture

Just culture is an approach to accountability after failure, developed in
aviation and adopted across health care and increasingly in software operations.
It rejects both extremes: the blame culture that punishes error, and the
blame-free culture that ignores genuine recklessness.

Core position: **most errors are produced by systems, and individual
accountability still exists — but it attaches to behavioral choices, not to
outcomes.**

**Evidence: Moderate.** Well grounded in safety science and human factors
research, which robustly supports the core premise that most errors are
system-produced and that punishing error suppresses reporting without reducing
error. Direct outcome evidence for just culture programs specifically is limited
and confounded, since they are rarely implemented alone. The three-behavior
classification is a decision aid with fuzzy boundaries, and can be applied
post-hoc to justify a decision already made.

Use when: designing incident response, after a serious failure, or when
reporting rates are low and you suspect fear.

Do not use when: substituting for system redesign. Just culture governs how you
treat people; it does not fix the system that produced the error.


## The three behaviors

David Marx's widely used classification:

1. **Human error** — an inadvertent slip, lapse, or mistake. Doing other than
   what should have been done, unintentionally. **Response: console.** Then fix
   the system that made the error likely and its detection unlikely. Punishing
   human error is both unjust and useless: it does not reduce error, it reduces
   reporting.

2. **At-risk behavior** — a choice that increases risk where the risk is not
   recognized or is mistakenly believed justified. Drifting from procedure
   because it is slow and nothing bad has happened yet. **Response: coach.**
   Understand why the shortcut was rational locally, and remove the incentive.
   At-risk behavior is usually a system signal: if everyone drifts the same way,
   the procedure is the problem.

3. **Reckless behavior** — conscious disregard of a substantial and
   unjustifiable risk. **Response: discipline.** Rare, and genuinely warranted
   when present.


## The substitution test

Before attributing an outcome to an individual, ask: would three other similarly
trained, similarly experienced peers, in the same situation with the same
information and the same pressures, have done the same thing?

If yes, the individual is not the cause. This test is the single most useful
tool in the set, and it survives contact with lawyers and regulators.


## The outcome bias problem

Identical decisions are judged differently depending on how they turned out. The
nurse who is interrupted during a drug round and administers correctly is
invisible; the one who errs is investigated. Same system, same behavior,
different luck.

Just culture requires judging the *behavior* and the *decision process*, not the
outcome. This is genuinely hard when the outcome is a death, and it is exactly
then that it matters most.


## Implementation requirements

* A published algorithm or decision tree applied consistently, so people can
  predict how they will be treated. Predictability *is* the mechanism.
* Consistency across seniority. If a junior is disciplined and a consultant is
  not for the same behavior, the policy is dead and everyone knows it.
* Separation of learning review from any disciplinary process, with different
  people, different timing, and a clear statement of which is happening.
* Managers trained in the distinctions, not just given a policy document.
* Protection of the reporter, stated and honored.


## Examples by audience

* **Health care**: the originating domain. Medication administration errors are
  overwhelmingly system-produced — look-alike packaging, interruption-heavy
  environments, understaffing, poor handover. Suspending the nurse removes one
  person and leaves the system that will produce the next error, while ensuring
  the next one is not reported.

* **Software**: an engineer runs a command that deletes production data. Just
  culture asks why the command was available, why it required no confirmation,
  why the backup was untested, and why one person could do it alone. "Fired the
  engineer" means the organization purchased no safety and lost the person who
  now understands the failure best.

* **Executive**: the executive test is what happens the first time a serious
  failure is publicly embarrassing. Every prior statement about learning culture
  is settled in that moment, and the organization will calibrate on it for
  years.


## Limitations

* The three-category scheme has fuzzy boundaries in practice, and the
  classification can be applied post-hoc to justify a decision already made.
* Regulatory, legal, and media pressure push hard toward individual blame.
* Requires managerial consistency that is difficult to sustain across a large
  organization.


## See also

* [westrum-organizational-culture-typology](../westrum-organizational-culture-typology/)
* [psychological-safety](../psychological-safety/)
* [high-reliability-organizations](../high-reliability-organizations/)
* [after-action-review](../after-action-review/)
* Sidney Dekker, *Just Culture*; David Marx, *Patient Safety and the Just
  Culture*.
