# Goal setting theory

Edwin Locke and Gary Latham's goal setting theory, developed from the 1960s
onward, holds that **specific and difficult goals produce higher performance
than vague or easy ones**, provided the person is committed to the goal and
receives feedback on progress toward it.

It is among the most extensively tested findings in organizational psychology,
supported by hundreds of studies across laboratory and field settings, and it
underlies most performance management practice — usually in a degraded form.

**Evidence: Strong.** Several hundred studies and multiple meta-analyses across
tasks, settings, and cultures, with effects that hold in field research and not
only in the laboratory. Among the best-supported findings in the whole field.
The boundary conditions are equally well established and are routinely ignored
in practice: the effect depends on commitment, feedback, and task complexity,
and it reverses in identifiable circumstances described below.

Use when: performance on a well-understood task is the problem, the person has
the ability to do it, and progress can be observed.

Do not use when: the task is novel or complex and the method is not yet known;
when the goal would be imposed without commitment; when performance cannot be
measured without distorting it. In those cases set a **learning goal** instead,
or do not set a goal at all.


## The core findings

1. **Specific beats vague.** "Reduce door-to-antibiotic time to 45 minutes"
   outperforms "improve sepsis care". "Do your best" is the weakest instruction
   in the literature, and it is the most common one given.

2. **Difficult beats easy** — up to the limit of ability. Performance rises with
   goal difficulty in a near-linear relationship until the person can no longer
   do the task, at which point it falls off sharply.

3. **Commitment is a necessary condition.** A difficult goal the person has not
   accepted produces no effect, or a negative one. Commitment rises with
   perceived importance and self-efficacy, and participation in setting the goal
   matters mainly because it raises both.

4. **Feedback is a necessary condition.** Goals without progress information do
   not work. This is the requirement most often omitted, because feedback is
   expensive and goals are cheap.

5. **The mechanisms are four.** Goals direct attention toward relevant activity
   and away from irrelevant activity; they energize effort; they increase
   persistence; and they prompt the search for task-relevant strategies. The
   fourth is why goals fail on complex tasks — the search for strategy consumes
   the attention the task needs.


## Learning goals versus performance goals

The distinction that matters most in knowledge work, and the one usually missed.

* A **performance goal** specifies an outcome: "reduce lead time to three days."
  It works when the method is known and the person can execute it.
* A **learning goal** specifies discovery: "identify and test three causes of
  our deployment delay." It works when the method is *not* known.

Setting a performance goal on a task whose method is unknown reliably degrades
performance, because attention goes to the outcome rather than to the strategy
search the task actually requires. This is the single most common goal setting
error in knowledge work, and it looks like a motivation problem when it is a
goal-type problem.


## When goal setting goes wrong

Ordóñez, Schweitzer, Galinsky, and Bazerman's critique — "Goal setting gone
wild" — documents the side effects, all of which follow from mechanism 1,
attention direction:

* **Narrowed focus.** Unmeasured dimensions of the work degrade. See
  [measurement-and-metrics](../measurement-and-metrics/).
* **Unethical behavior.** Goals just out of reach, with consequences attached,
  reliably increase misreporting and corner-cutting.
* **Risk distortion.** People take excessive risk when close to a goal they will
  otherwise miss.
* **Reduced intrinsic motivation.** Especially where the goal is imposed and
  tied to reward. See
  [self-determination-theory](../self-determination-theory/).
* **Corrosion of cooperation.** Individual goals in interdependent work create
  competition where collaboration is required.

The countermeasures are not subtle: use goal ranges rather than points, pair
every output goal with a quality and a balancing measure, avoid attaching
individual financial consequence to a single number, and never set a stretch
goal on a task where failure is catastrophic.


## Relationship to targets and metrics

Goal setting theory says goals work. **Goodhart's law says that a measure used
as a target stops being a good measure.** Both are true, and the resolution is
practical: goals change behavior effectively, which is exactly why a badly
chosen goal changes behavior effectively in the wrong direction.

Practical rules that follow:

* Set goals on things you want more of, not on proxies for them.
* Pair every goal with a balancing measure.
* Use goals to direct attention, not to allocate individual reward, wherever the
  work is interdependent.
* Prefer team-level goals in knowledge work.


## Examples by audience

* **Health care**: sepsis bundles are goal setting done well — specific,
  difficult, measurable, with rapid feedback and clinician commitment. Four-hour
  emergency department targets are goal setting done badly: a single number with
  consequences attached, producing the documented distortion of patients
  reclassified or moved to corridors to stop the clock. Same theory, opposite
  outcome, and the difference is whether a balancing measure existed.

* **Software**: "reduce p95 latency to 200 ms" is a performance goal and works
  where the team knows how. "Find out why the checkout path is slow and report
  three candidate causes" is a learning goal and works where they do not.
  Velocity targets are the classic failure: a proxy, at individual or team
  level, with no balancing measure, and it inflates immediately.

* **Executive**: OKRs are goal setting theory with the boundary conditions
  stripped out. The theory requires commitment and feedback; quarterly OKRs
  cascaded downward supply neither, and the ambition norm — "if you hit 100% you
  set them too low" — deliberately breaks the commitment condition. If you use
  OKRs, restore the two missing conditions rather than adding more ceremony.


## Limitations

* Effects are strongest on tasks that are well understood and reasonably simple,
  which describes less knowledge work than managers assume.
* Most of the field research measures performance over weeks, not years; the
  long-run side effects are less well studied than the short-run gains.
* The theory says little about which goals are worth pursuing. It is a theory of
  execution, not of direction.


## See also

* [self-determination-theory](../self-determination-theory/) — why imposed,
  reward-linked goals undermine motivation for interesting work.
* [job-characteristics-model](../job-characteristics-model/) — feedback from the
  work itself, which is the cheapest way to satisfy the feedback condition.
* [measurement-and-metrics](../measurement-and-metrics/) — Goodhart's law and
  balancing measures.
* [improvement-kata](../improvement-kata/) — target conditions, which are
  learning goals with a deadline.
* Locke & Latham, *A Theory of Goal Setting and Task Performance*.
* Ordóñez et al., "Goals gone wild" (2009).
* <https://github.com/joelparkerhenderson/objectives-and-key-results>
* <https://github.com/joelparkerhenderson/smart-criteria>
