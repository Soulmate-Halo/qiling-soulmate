<p align="center">
  <img src="assets/soulmate-logo.png" alt="器灵 Soulmate" width="180" />
</p>

<h1 align="center">器灵 Soulmate</h1>

<p align="center">
  <strong>Orchestrate multiple AI coding assistants into a local team that truly works in parallel.</strong><br />
  Decompose tasks, route them dynamically, govern context, and keep every step economical.
</p>

<p align="center">
  <strong>English</strong> | <a href="README_CN.md">简体中文</a>
</p>

<p align="center">
  <a href="https://qiling.swcbg.com">Website</a> ·
  <a href="docs/ROADMAP.md">Roadmap</a> ·
  <a href="https://github.com/Soulmate-Halo/qiling-soulmate/issues">Issues</a> ·
  <a href="https://github.com/Soulmate-Halo/qiling-soulmate/discussions">Discussions</a>
</p>

---

## What it is

器灵 Soulmate (Soulmate) is a **local-first** AI programming assistant product. Instead of running one assistant at a time, it coordinates several AI coding tools inside a single session — assigning work, watching what each one is doing, and merging the results into one finished job.

It is designed around four ideas:

- **Multi-CLI orchestration** — several AI coding assistants work in one session, both divided and coordinated;
- **Task decomposition** — a large request is broken into independent, machine-verifiable sub-tasks;
- **Dynamic routing** — each sub-task is handed to an idle executor based on its type, dependencies, and concurrency limits;
- **Context & cost governance** — only the necessary content enters the context, large files are read on demand, and delegable work is pushed out to sub-agents.

Soulmate runs as a desktop application and works directly on your machine, including browser automation via CDP / Selenium / Playwright.

## Three routes: Fast · Accurate · Economical

Soulmate's orchestration philosophy balances three emphases. They are design choices, not benchmark promises:

| Route | What it means in practice |
| --- | --- |
| **Fast** | Executors run in parallel instead of waiting in line; independent sub-tasks proceed side by side rather than sequentially. |
| **Accurate** | Tasks are decomposed into machine-verifiable units, and the right content is kept in context — so the result is checked by execution, not by re-reading. |
| **Economical** | Exploration and coding that can be delegated are handed to sub-agents in one step; machine verification replaces manual re-reading, keeping per-step cost low. |

You can lean toward any of the three depending on the job — Soulmate does not force a single mode.

## How it works

```mermaid
flowchart LR
  A[You describe the task] --> B[Decompose into sub-tasks]
  B --> C[Route to idle executors]
  C --> D[Executors work in parallel]
  D --> E[Machine verification]
  E --> F[Result delivered]
```

The steps above describe the product's working philosophy. The internal implementation of the orchestration strategy remains closed source.

## Getting started

Soulmate is a commercial desktop product — this repository is its community and operations entry point, not a source distribution.

- **Learn about the product** — visit the official website: <https://qiling.swcbg.com>
- **Understand the boundary** — read [docs/OPEN_SOURCE_SCOPE.md](./docs/OPEN_SOURCE_SCOPE.md) to see what this repository opens and what stays closed
- **See the public roadmap** — read [docs/ROADMAP.md](./docs/ROADMAP.md)
- **Report a bug or request a feature** — use the [Bug template](./.github/ISSUE_TEMPLATE/bug_report.yml) or the [Feature request template](./.github/ISSUE_TEMPLATE/feature_request.yml)
- **Report a security issue** — use GitHub's private reporting channel; never post vulnerability details in a public issue (see [SECURITY.md](./SECURITY.md))

## Repository scope

This repository is the **community and operations entry point** for 器灵 Soulmate. It is **not** an open-source software repository and does not ship product source code. The desktop core runtime, orchestration strategy, commercial server-side, and production configuration remain **closed source**.

| Open | Closed |
| --- | --- |
| Product positioning and usage philosophy | Desktop core runtime |
| Public roadmap | Orchestration strategy and internal implementation |
| Issue feedback and community collaboration | Commercial server-side |
| Community discussion | Production configuration and deployment details |

The full boundary is described in [docs/OPEN_SOURCE_SCOPE.md](./docs/OPEN_SOURCE_SCOPE.md).

## Community

We welcome documentation improvements, feedback, and collaboration — but please note the boundary above.

- **Issues** — report bugs and request features through the templates above
- **Discussions** — share experiences and discuss directions
- **Pull Requests** — read [CONTRIBUTING.md](./CONTRIBUTING.md) before opening one, and use the [PR template](./.github/PULL_REQUEST_TEMPLATE.md)

Please do **not** submit product core source code, keys, credentials, internal server information, or download links in this repository.

## Links

| Link | Purpose |
| --- | --- |
| <https://qiling.swcbg.com> | Official website |
| [docs/ROADMAP.md](./docs/ROADMAP.md) | Public roadmap |
| [docs/OPEN_SOURCE_SCOPE.md](./docs/OPEN_SOURCE_SCOPE.md) | Open-source scope and boundary |
| [SECURITY.md](./SECURITY.md) | Security policy |
| [CONTRIBUTING.md](./CONTRIBUTING.md) | Contribution guide |
| [NOTICE.md](./NOTICE.md) | Copyright and trademark notices |
