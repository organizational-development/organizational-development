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

Then update the check count in this file's table, in
[../AGENTS.md](../AGENTS.md#validation), and in
[../spec/conventions.md](../spec/conventions.md#validation).

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
  grep -h -o '^\*\*Evidence: [^.]*\.' topics/*/index.md |
    sed 's/\*\*Evidence: //; s/\.$//' | sort | uniq -c | sort -rn
  ```

* **Are there near-duplicate topics** that should be merged?
* **Is `README.md` still self-contained**, or has content drifted into `topics/`
  that the guide now assumes?
* **Are the tasks in `spec/index.md` current**, or does it claim work is
  outstanding that is done?

Record the outcome of a manual pass in `spec/index.md` rather than leaving it in
a commit message.
