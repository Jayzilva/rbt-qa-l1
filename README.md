# rbt-qa-l1 — QA Engineer track (QA-L1)

My work for the BISTEC Academy role-based training **QA Engineer** track: six modules, each a
self-contained project built spec-first with [specclaw](https://github.com/Jayzilva/specclaw)
(teaching mode on), shipped as one reviewed pull request, and written up publicly.

Carry-through app: ShopEasy (tested across modules).

## Modules

| ID | Module | Scheduled | Headline target | Status | PR | Video | Post |
|---|---|---|---|---|---|---|---|
| QA-L1-M01 | Testing Fundamentals | Fri 2 Oct 2026 | test cases + defects | Not started | – | – | – |
| QA-L1-M02 | Test Automation Basics | Sat 3 – Sun 4 Oct 2026 | automated suite | Not started | – | – | – |
| QA-L1-M03 | API Testing | Fri 9 – Sat 10 Oct 2026 | API suite + contracts | Not started | – | – | – |
| QA-L1-M04 | Performance Testing | Sun 25 Oct 2026 | load test report | Not started | – | – | – |
| QA-L1-M05 | Mobile & Security Testing | Fri 6 – Sat 7 Nov 2026 | OWASP findings | Not started | – | – | – |
| QA-L1-M06 | Test Strategy & Leadership (capstone) | Sun 8 Nov 2026 | test strategy | Not started | – | – | – |

A module is done only when its PR is approved. Status values: Not started, Ready, Studying, Building,
Verifying, In review, Approved. A title becomes a link when its folder is created.

## How this repo works

- **One folder per module**, created on its start day with `node tools/start-module.mjs mNN`
  (or `/start-module mNN` in Claude Code at the repo root). Each folder has its own `CLAUDE.md`,
  `.claude/` rules and skills, `memory/`, `.specclaw/` and docs, so it works on its own:
  `cd mNN-* && claude`.
- **Spec-driven**: propose → teach → plan → build → verify → pr, one specclaw change per module.
- **Learning first**: teaching mode briefs unfamiliar concepts and hands design decisions to me.
- **Review**: PR titled `<MODULE-ID> <Title>`, self-scored against the rubric; reviewer: QA.
  After approval: merge, tag `<module-id>-v1`.

## Connected content

Every module links three ways: this repo ↔ a NotebookLM video on YouTube ↔ the weekly Substack
build log. Links live in the table above and in each module's README.

## Publishing

Academy material is confidential and never committed (`.academy/` and `*/academy/` are
gitignored). Only each module's `docs/PUBLIC.md` feeds public content.

- [ ] Written OK from the academy owner to publish build logs and videos (date, who):

## Setup after a fresh clone

    ACADEMY_PASSWORD=... node tools/fetch-academy.mjs      # decrypt track pages into .academy/
    node tools/start-module.mjs m01 --refresh-academy     # restore a module's academy/ files

Requires Node 18+. Pandoc is optional (better Markdown). Claude Code picks up the specclaw
plugin from each module's `.claude/settings.json`.
