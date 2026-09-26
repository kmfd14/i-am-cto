# i-am-cto

![i-am-cto wordmark and iron-law tagline](assets/banner.svg)

[![License: MIT](https://img.shields.io/github/license/kmfd14/i-am-cto)](LICENSE.md)
[![Last commit](https://img.shields.io/github/last-commit/kmfd14/i-am-cto)](https://github.com/kmfd14/i-am-cto)

> [!NOTE]
> This skill tells the agent how to choose an architecture. It does not pretend to be an executive.

Work like a practical CTO. Choose the simplest system that does the job, that this team can put in production and fix if it breaks, and that you can undo if the choice was wrong. Be ready to explain why.

**Iron law:** Use the simplest production setup that still does the job.

## What it does

- Sorts the change: easy to undo, hard to undo, an outage right now, or a short experiment
- Compares at least three options: wait, smallest change, bigger change
- Scores those options on what matters here, including how hard it is to run and to undo
- Says how it fails, how you notice, how you roll back, and who is on call
- Ships the smallest piece that proves the decision was right
- For hard-to-undo changes, writes a short decision record (an ADR)

## Install

1. Open a terminal.
2. Run:

```bash
npx skills add kmfd14/i-am-cto -g -y
```

3. Confirm the skill appears for your agent (Cursor, Claude Code, or similar).

Local path (no GitHub clone):

```bash
npx skills add /path/to/i-am-cto -g -y
```

## Quick Start

After install, ask the agent something that needs a real architecture call:

```text
Act as CTO. We need in-app and email notifications on comments.
Stack is Next.js + Postgres, two engineers, three days.
Someone suggested Kafka. Run the options table and give a verdict.
```

Other triggers that should load this skill:

- Review this approach before we add a queue or a new service.
- Write an ADR for the tenancy change.
- Build vs buy for auth: what is the cheapest sufficient path?

## Operating loop

```text
read the repo -> state the job
        -> easy or hard to undo -> compare options -> pick one
        -> how to run and roll back -> smallest piece -> check it
```

1. Read the repo. Name the real parts. Do not invent scale.
2. Say the job and the hard limits (time, team, stack, budget).
3. Say whether the change is easy or hard to undo.
4. List options and score the ones that matter.
5. Pick one decision and say how you will run and roll it back.
6. Define the smallest shippable piece and check that it works.

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
