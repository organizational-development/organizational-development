# Playbook: audit

Running, interpreting, fixing, and extending `bin/audit`.


## Run it

```sh
bin/audit           # full report, section by section
bin/audit --quiet   # failures only; use in CI and pre-commit hooks
```

Exit 0 means clean. Exit 1 means violations. Exit 2 means the script could not
find the repository root.

Run it before every commit. Do not commit a failing tree.


## What it checks

| # | Check | Catches |
| --- | --- | --- |
| 1 | Topic directory structure | Missing `index.md`; missing or wrong `README.md` symlink |
| 2 | One level-one heading per topic | Two topics merged into one file |
| 3 | Evidence labels present and permitted | Unrated models; invented strength values |
| 4 | `Use when` and `Do not use when` | Advocacy without a boundary |
| 5 | Questionnaire pairing, both directions | Orphan questionnaires; missing analysis section |
| 6 | Cross-topic links resolve | Renamed or deleted topics |
| 7 | No legacy bare `.md` sibling links | Links from the pre-`topics/` layout |
| 8 | README links resolve | Stale links after a rename |
| 9 | README anchors resolve | Contents entries pointing at renamed headings |
| 10 | Agent files under 40 KB | Agent context bloat |
| 11 | `topics/index.md` completeness | Topics that exist but are unlisted |
| 12 | Required top-level files present | A deleted `CONTRIBUTING.md`, CI workflow, or `topics/README.md` symlink |
| 13 | Stated model count matches reality | "Across 68 models" after the count reached 72 |
| 14 | All three audience examples | A topic written for one audience only |
| 15 | No orphan topics | A topic no sibling links to, reachable only from the index |
| 16 | Prose wrapped at 80 columns | Unwrapped paragraphs that make diffs unreadable |
| 17 | Check list in `spec/conventions.md` matches | A check added to the script and not documented |
| 18 | This table documents every check | This table going stale, which it did once |
| 19 | Stated check counts match the script | A spelled-out or numeric count in prose left behind when the script grew |


## Fixing each failure

**1. Missing symlink**

```sh
cd topics/<name> && ln -sfn index.md README.md && cd ../..
```

**2. Multiple level-one headings.** The file is two topics. Split it, or demote
the second heading to `## `.

**3. Missing or unrecognized evidence label.** See
[evidence-labels.md](evidence-labels.md). There is no unrated state. If the
strength value is unrecognized, either use a permitted one or add the new value
to both `spec/conventions.md` and the `EVIDENCE_RE` in `bin/audit`.

**4. Missing `Use when` / `Do not use when`.** Both are required, as plain
paragraphs and not headings, immediately after the evidence block. If you cannot
write the second one, you do not understand the model well enough yet.

**5. Questionnaire pairing.** Add the `## Questionnaire` section to the model,
the `../<model>/` link back from the questionnaire, or the closing analysis
section. See [add-a-questionnaire.md](add-a-questionnaire.md).

**6, 7, 8. Broken links.** Usually a rename. Find and fix every reference:

```sh
grep -rn "old-topic-name" topics/ README.md spec/ AGENTS/ AGENTS.md
```

Cross-topic links are `../<topic>/`. Never `foo.md`, never `../foo/index.md`.

**9. Broken README anchor.** A heading was renamed but its contents entry was
not. GitHub derives the anchor by lowercasing, stripping punctuation, and
replacing spaces with hyphens.

**10. Oversized agent file.** Split it into a new `AGENTS/` playbook and link
from `AGENTS.md`. Do not compress by deleting the reasoning; the reasoning is
what makes a playbook usable.

**11. Unlisted topic.** Add it to `topics/index.md` in the right family, with
its evidence label in brackets.

**12. Missing required file.** Restore it. The list is deliberately short —
`README.md`, `AGENTS.md`, `CLAUDE.md`, `CONTRIBUTING.md`, `LICENSE.md`,
`spec/index.md`, `spec/conventions.md`, `topics/index.md`, the CI workflow, and
the `topics/README.md` symlink. Each is load-bearing for someone: a reader, an
agent, a contributor, or CI.

**13. Stale model count.** A count in prose no longer matches the tree. Recount
with the command under [Beyond the script](#beyond-the-script) and update every
file the check names. Do not adjust a number by hand from memory.

**14. Missing audience example.** The guide serves health care, software, and
senior executives, and a topic that speaks to one of them is half-written. Add
the missing example and make it specific enough to picture — see
[style-guide.md](style-guide.md#audience-examples).

**15. Orphan topic.** No sibling links to it, so a reader browsing by
association will never arrive. Add `../<topic>/` links from at least one related
topic — usually the one a reader would be reading when they need this. If no
sibling wants to link to it, ask whether it should be a section inside an
existing topic instead.

**16. Long prose line.** Hard-wrap at 80 columns. Tables, fenced code, URLs, and
a line that is a single markdown link are exempt, and the check already skips
them.

**17, 18, 19. Self-documentation drift.** The check list in
`spec/conventions.md`, the table in this file, and every "<n> checks" claim in
prose must all agree with the `section` calls in `bin/audit`. Fix the
documentation, in all three places, rather than the script — unless the script
is what is wrong. These checks exist because this file once documented eleven
checks while the script had seventeen, which is the worst place for a stale
fact: it is what an agent reads *because* a check just failed.

A note on the wording of check 19: it skips lines written in the past tense, so
that a record like "claimed 11 checks; it had 16" can stay. Write history in the
past tense and current fact in the present, and the check does the right thing.


## Extending the checks

Add a check when a class of mistake has occurred twice.

The pattern:

```bash
# ------------------------------------------------------------- N. description
section "N. Human-readable name"
before=$FAIL
for t in $TOPICS; do
  is_questionnaire "$t" && continue      # skip where the rule does not apply
  grep -q 'pattern' "topics/$t/index.md" || fail "topics/$t/index.md: what is wrong"
done
[ "$FAIL" -eq "$before" ] && pass
```

Then document it in this file — a table row *and* a "Fixing each failure"
entry — in [../spec/conventions.md](../spec/conventions.md#validation), and in
the prose counts in [../AGENTS.md](../AGENTS.md#validation) and
[../CONTRIBUTING.md](../CONTRIBUTING.md#validation). Checks 17, 18, and 19 fail
until you do, so the audit tells you what you forgot rather than leaving it to
the next reader to discover.

**Constraints on new checks:**

* **No false positives.** A check that cries wolf gets ignored, then disabled.
  Test against the full tree before committing it.
* **Name the file and say what is wrong**, in terms the fixer can act on.
* **Do not check style that a human should judge.** Prose quality, example
  specificity, and evidence-rating accuracy are editorial, not mechanical.
* **Keep it fast.** The whole run should stay under a couple of seconds so that
  people actually run it.


## Two traps, both already hit

**Do not shadow shell builtins.** An early version defined a function named
`head`, which shadowed `head -3` inside another check and produced 97 false
failures. The function is now `section`. Avoid `head`, `tail`, `test`, `printf`,
`echo`, `set`.

**Case sensitivity.** Check 5 originally matched `^## .*Analysis` and failed a
correctly sentence-cased `## Step 5: Causal analysis`. Conventions require
sentence case, so the check uses `grep -qi`. When a check disagrees with
`spec/conventions.md`, **the check is the bug** — fix the script, not the
content.


## Beyond the script

Some things cannot be mechanically checked and need a periodic human pass:

* **Evidence ratings still accurate?** New research appears. A `Weak` rating
  from a year ago may now be `Moderate`, or vice versa.
* **Are the three audience examples genuinely specific**, or have generic ones
  crept in?
* **Do the three evidence tables agree** with the topic files? Recount:

  ```sh
  find topics -name index.md -not -path '*-questionnaire/*' \
    -exec grep -h -m1 -o '^\*\*Evidence: [^.]*\.' {} + |
    sed 's/\*\*Evidence: //; s/\.$//' | sort | uniq -c | sort -rn
  ```

  Questionnaires are excluded because each inherits its model's rating;
  counting them disagrees with the documented model-only distribution.

* **Are there near-duplicate topics** that should be merged?
* **Is `README.md` still self-contained**, or has content drifted into `topics/`
  that the guide now assumes?
* **Are the tasks in `spec/index.md` current**, or does it claim work is
  outstanding that is done?

Record the outcome of a manual pass in `spec/index.md` rather than leaving it in
a commit message.
