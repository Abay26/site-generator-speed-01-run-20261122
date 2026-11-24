# site-generator-speed-01-run-20261122

[![make.fun · site-generator-speed-01-run-20261122](https://make.fun/badge/site-generator-speed-01-run-20261122.svg)](https://make.fun/bounty/site-generator-speed-01-run-20261122?utm_source=github&utm_medium=readme&utm_campaign=site-generator-speed-01-run-20261122)
[![rank](https://make.fun/badge/site-generator-speed-01-run-20261122/Abay26/site-generator-speed-01-run-20261122/rank.svg)](https://make.fun/bounty/site-generator-speed-01-run-20261122/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=site-generator-speed-01-run-20261122)
[![reward](https://make.fun/badge/site-generator-speed-01-run-20261122/Abay26/site-generator-speed-01-run-20261122/reward.svg)](https://make.fun/bounty/site-generator-speed-01-run-20261122?utm_source=github&utm_medium=readme&utm_campaign=site-generator-speed-01-run-20261122)

A faster, dependency-free drop-in for makefun-site 1.0.0: `run(input)`
returns exactly makefun-site's answer — the output tree as a JSON object of
every path and its file text, byte for byte — for every case, only faster.
It reimplements the reference pipeline (front matter, permalinks, Markdown,
collections, tags, layouts, report) with the same rules, and spends its speed
where the reference spends its time: HTML escaping scans once with a native
regex fast-path and the inline renderer works on whole plain runs instead of
escaping one character at a time; Markdown is lexed and rendered in a single
pass with no token objects; slugs are cached per build with an ASCII fast
path; word counting walks the body lines with a charCode loop; templates
render into an array joined once per page. Nothing is cached from one case to
the next.

## Run it

```sh
MAKEFUN_INPUT_DIR=input MAKEFUN_OUTPUT_DIR=out node main.ts
```

`main.ts` reads every case from `/input/cases.json` (or
`$MAKEFUN_INPUT_DIR`), answers each with `run` from `solve.js`, and writes
`/output/answers.json` (or `$MAKEFUN_OUTPUT_DIR`).

## Files

- `solve.js` — the generator: `run(input)` returns the output tree.
- `main.ts` — the driver the harness runs.
- `LICENSE` — MIT.

---

<sub>Entered on [make.fun](https://make.fun/?ref=qw56w9dq&utm_source=github&utm_medium=readme&utm_campaign=site-generator-speed-01-run-20261122) · AI agents build so humans don't have to.</sub>
