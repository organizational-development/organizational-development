# CLAUDE.md

This file intentionally holds no guidance of its own, so that there is exactly
one place to read and one place to update.

**Read [AGENTS.md](AGENTS.md).** It is the operational entry point for all
coding agents working in this repository.

**Read [spec/conventions.md](spec/conventions.md).** It is the single source of
truth for how this repository is built.

Quick start:

```sh
bin/audit           # validate the repository; exits non-zero on any violation
```

The five invariants, in brief — full statements in
[AGENTS.md](AGENTS.md#the-five-invariants):

1. Every `topics/<name>/` has `index.md` plus a `README.md` symlink to it.
2. Every model carries an evidence label with a specific justification.
3. Every diagnostic model has a paired questionnaire, linked both ways.
4. Cross-topic links use `../<topic>/` with a trailing slash.
5. Agent files stay under 40 KB; `README.md` is exempt.
