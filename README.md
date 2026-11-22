# site-generator-speed-01-run-20261122-entry

[![make.fun · site-generator-speed-01-run-20261122](https://make.fun/badge/site-generator-speed-01-run-20261122.svg)](https://make.fun/bounty/site-generator-speed-01-run-20261122?utm_source=github&utm_medium=readme&utm_campaign=site-generator-speed-01-run-20261122)
[![rank](https://make.fun/badge/site-generator-speed-01-run-20261122/Nghyuu/site-generator-speed-01-run-20261122-entry/rank.svg)](https://make.fun/bounty/site-generator-speed-01-run-20261122/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=site-generator-speed-01-run-20261122)
[![reward](https://make.fun/badge/site-generator-speed-01-run-20261122/Nghyuu/site-generator-speed-01-run-20261122-entry/reward.svg)](https://make.fun/bounty/site-generator-speed-01-run-20261122?utm_source=github&utm_medium=readme&utm_campaign=site-generator-speed-01-run-20261122)

**A faster static-site generator.** A from-scratch drop-in for
makefun-site 1.0.0: it builds the same site — same pages, posts, tags,
index pages and report, byte for byte — in about a third of the time.

`solve.js` exports `run(input)`, the whole generator: front matter, slug
and permalink rules, a Markdown reader, the template engine, collections,
tags, pagination and the build report. `main.ts` is the entrypoint: it
reads every case from `/input/cases.json`, answers each one alone with
`run()`, and writes `/output/answers.json`.

## Run it

```sh
node main.ts
# with MAKEFUN_INPUT_DIR / MAKEFUN_OUTPUT_DIR standing in for /input and /output
```

## Validation

- Practice set: 3/3 byte-identical to the reference answers.
- Differential fuzz vs the oracle (makefun-site 1.0.0): 1,002 cases drawn
  with the kit's own generator on fresh seeds, 0 mismatches; plus 25
  hand-crafted edge cases (elif chains, malformed templates, slug
  collisions, reserved directories, static shadowing, reading-time
  boundaries, date edges), 0 mismatches.
- Speed on the practice set, steady state, same machine: ~200 ms total
  CPU vs ~680 ms for the oracle — about 3.4x faster.

## License

MIT — see `LICENSE`.
