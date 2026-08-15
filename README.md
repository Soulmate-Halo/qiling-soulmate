<p align="center">
  <img src="assets/soulmate-logo.png" alt="器灵 Soulmate" width="180" />
</p>

<h1 align="center">器灵 Soulmate</h1>

<p align="center">
  <strong>Strong models as the brain, weak models as the hands — multiple Agent CLIs in one workbench.</strong><br />
  Choose one: fast, accurate, or economical.
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

## A note from the author

I am an independent developer. The AI era gave me a lot of inspiration and made development unprecedentedly efficient; but the high subscription fees and API costs kept bothering me. Every time a new model appeared, I almost had to subscribe to another service, and the old subscription was soon left idle. I also deployed many models locally, but apart from being free, they struggled to be useful in real development work.

So I kept breaking down the differences between strong and weak models on tool calls, file reading and other metrics. In the end I reached a conclusion: **let the strong model be the brain — decomposing tasks, judging direction and doing final verification; let the weak model be the hands — file reading, retrieval, repetitive execution and bulk output.** I built this Agent CLI, and after countless rounds of testing and rule fixes, this collaboration finally worked.

With the compression rules I designed — I call it 器灵压缩 (Qiling Compression) — the combination of main and collaborative models can greatly reduce the main model's consumption while keeping precision; in some tasks, speed and result quality even exceed the strong model working alone. I also connected the CLIs I commonly use into the same workbench, keeping the collaborative gains while preserving my original habits. If you are a heavy user of AI Agents, you are welcome to join me and raise a Qiling (器灵) of your own.

## What it is

器灵 Soulmate (Soulmate) is a **local-first** AI programming assistant product. Instead of running one assistant at a time, it gathers several Agent CLIs into a single workbench — you pick, route, and observe them side by side, so one channel going down never takes the rest with it.

Its core idea is simple: **strong models do the thinking, weak models do the legwork.** Strong models handle task decomposition, direction and final verification; weak models handle file reading, retrieval, repetitive execution and bulk output. A dedicated compression layer keeps the strong model's context small without losing precision.

Soulmate runs as a desktop application and works directly on your machine, including browser automation via CDP / Selenium / Playwright.

## Choose one route: Fast · Accurate · Economical

> **Choose exactly one route.** Pick the single route that fits your current primary goal — the three are not enabled at the same time, nor run one after another.

| Route | When to pick it | Primary goal |
| --- | --- | --- |
| **Fast** | The job is taking too long | Speed it up |
| **Accurate** | The result must be reliable | Raise quality |
| **Economical** | The cost is too high | Spend less |

Pick **one** route per task, according to your current primary goal. The numbers below are **product-side estimates from the official website scenarios**, not customer testimonials or universal promises.

### Fast — scout the big repo first, then let the strong model act

In an unfamiliar repository, the task is decomposed into scout ranges, several sub-agents search in parallel, and the strong model receives the condensed key evidence before it starts editing.

- Example (official website scenario): 4 parallel tasks cut a job from **18 minutes to 7 minutes**, about **2.6× faster**.

### Accurate — find counterexamples in parallel, let the expensive model only arbitrate

Before a high-requirement delivery, evidence is cross-checked along separate paths, counterexamples are collected, and the final call is a consensus ruling backed by machine verification (PASS/FAIL) by the strong model.

- Example (official website scenario): scoring goes from **86 to 94** under independent review plus machine verification.

### Economical — outsource mechanical steps, keep the expensive model from replaying

Mechanical steps such as retrieval, scanning, drafting and testing are handed to cheaper collaborative models, so the strong model reads less context and executes fewer tool calls.

- Example (official website scenario): cost drops from **100 to 41 cost units**, saving **59%**.

For conversation baselines, the official website estimates savings of **8–25%** for short dialogues (1–3 effective rounds), **35–64%** for multi-round dialogues (4–14 effective rounds), and **51–82%** for long dialogues (15+ effective rounds). All figures are product-side estimates under fixed assumptions, not guarantees; real results vary with model, pricing, cache and task structure.

Whichever route you pick, remember: **Choose exactly one route** — align the whole task to your current primary goal, rather than enabling all three or running all of them in turn.

## How it works

```mermaid
flowchart LR
  A[You describe the task] --> B[Decompose into sub-tasks]
  B --> C[Route to idle executors]
  C --> D[Executors work in parallel]
  D --> E[Machine verification]
  E --> F[Strong model delivers the result]
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

## Release Policy

Soulmate ships releases as a **four-endpoint release transaction** with a fixed order (Local → paired content hot update when applicable → CN Website → GitHub → Overseas Website). Client hot update is a mandatory delivery track inside the transaction, not a fifth endpoint: the same change must pass machine verification on both paired content channels, and either-side failure rolls both manifests back. Documentation-only or website-only changes are recorded as **NOT_APPLICABLE_DOCS_ONLY**; empty update bundles are forbidden. See [docs/RELEASE_POLICY.md](./docs/RELEASE_POLICY.md) for the full public summary. The overseas website is currently **SKIPPED_NOT_OPEN / 未开放** and no release action is performed, simulated, or stubbed until it opens.

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
