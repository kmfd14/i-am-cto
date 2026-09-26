# i-am-cto

![i-am-cto wordmark and iron-law tagline](assets/banner.svg)

[![License: MIT](https://img.shields.io/github/license/kmfd14/i-am-cto)](LICENSE.md)
[![Last commit](https://img.shields.io/github/last-commit/kmfd14/i-am-cto)](https://github.com/kmfd14/i-am-cto)

> [!NOTE]
> This is a decision method for architecture and technical strategy. It is not executive roleplay or model-routing theater.

Operate as a working CTO: pick the cheapest sufficient system this team can ship, run at 3am, reverse if wrong, and defend in a design review.

**Iron law:** Ship the cheapest sufficient production-grade path.

## Tech stack

<img src="https://cdn.simpleicons.org/markdown/000000" alt="Markdown" width="28" height="28" />
<img src="https://cdn.simpleicons.org/python/3776AB" alt="Python" width="28" height="28" />

Markdown skill body, Python plan-heading check (`scripts/check_plan.py`).

## What it does

- Classifies work as a two-way door, one-way door, incident, or research spike
- Forces at least three options: postpone, smallest change, heavier change
- Scores options on quality attributes that matter for this job
- Writes a production contract: failure modes, SLIs, rollback, migration, on-call
- Ships a thin slice that can prove the verdict
- Requires a Nygard ADR for one-way doors

## Install

1. Open a terminal.
2. Run:

```ansi
[38;2;224;122;95m[1m$[0m npx skills add [38;2;224;122;95mkmfd14/i-am-cto[0m [38;2;202;138;4m-g[0m [38;2;202;138;4m-y[0m
```

3. Confirm the skill appears for your agent (Cursor, Claude Code, or similar).

Local path (no GitHub clone):

```ansi
[38;2;224;122;95m[1m$[0m npx skills add [38;2;224;122;95m/path/to/i-am-cto[0m [38;2;202;138;4m-g[0m [38;2;202;138;4m-y[0m
```

## Quick Start

After install, ask the agent something that needs a real architecture call:

```ansi
[38;2;224;122;95m[1mAct as CTO.[0m We need in-app and email notifications on comments.
Stack is Next.js + Postgres, two engineers, three days.
Someone suggested Kafka. [38;2;202;138;4mRun the options table and give a verdict.[0m
```

Other triggers that should load this skill:

- Review this approach before we add a queue or a new service.
- Write an ADR for the tenancy change.
- Build vs buy for auth: what is the cheapest sufficient path?

## Operating loop

```ansi
evidence [38;2;224;122;95m→[0m job/constraints [38;2;224;122;95m→[0m [38;2;202;138;4mdoor class[0m
        [38;2;224;122;95m→[0m options (≥3) [38;2;224;122;95m→[0m score [38;2;224;122;95m→[0m [38;2;202;138;4mverdict[0m
        [38;2;224;122;95m→[0m production contract [38;2;224;122;95m→[0m thin slice [38;2;224;122;95m→[0m [38;2;202;138;4mverify[0m
```

1. Read the repo. Name real modules, stores, APIs. Do not invent scale.
2. State the job and hard constraints.
3. Classify the door.
4. List options and score the attributes that matter.
5. Give one imperative verdict and a production contract.
6. Define the thin slice and verify it.

## Repo map

| Path | Role |
| --- | --- |
| [`SKILL.md`](SKILL.md) | Agent instructions and contracts |
| [`references/`](references/) | Quality attributes, threat model, ADRs, boring tech, delegation |
| [`assets/`](assets/) | ADR and plan templates, banner |
| [`scripts/check_plan.py`](scripts/check_plan.py) | Optional plan-heading check |

## Contributing

1. Fork the repository.
2. Create a feature branch.
3. Open a pull request.

## License

MIT. See [`LICENSE.md`](LICENSE.md).
