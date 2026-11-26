# Contributing

Thank you for helping build Limitless Learning. Participation is governed by our [Code of Conduct](./CODE_OF_CONDUCT.md).

## Quick start

1. Find work on the [project board](https://github.com/orgs/limitlesslearning/projects/1) or repo issues.
2. Prefer issues labeled `good first issue` or `help wanted` if you are new.
3. Comment on the issue asking to be assigned; wait for assignment before large work.
4. Fork the repo (or branch, if you have write access).
5. Create a branch: `type/short-description` (e.g. `docs/fix-typo`, `feat/add-node-api`, `fix/login-crash`).
6. Commit with [Conventional Commits](https://www.conventionalcommits.org/) and **DCO sign-off** (`git commit -s`).
7. Open a small, focused PR using the template; link the issue with `Closes #N`.

## Find and claim an issue

| Step | Detail |
| --- | --- |
| Discover | Board: [orgs/limitlesslearning/projects/1](https://github.com/orgs/limitlesslearning/projects/1). Filters: Status, Priority, Area, Phase, Size. |
| Newcomers | Label `good first issue` — scoped, documented, low risk. |
| Claim | Comment: “I’d like to work on this.” A maintainer/triager assigns you. |
| Scope | If the issue is unclear, ask before coding. Use `needs-info` / Status **Backlog** until clarified. |

Do not drive-by reassign others’ issues. If an assignee is inactive for a long time, comment and wait for a maintainer.

## Branch naming

```
type/short-description
```

Common `type` prefixes: `feat`, `fix`, `docs`, `content`, `chore`, `refactor`, `test`, `ci`, `rfc`.

## Conventional Commits

```
type(scope): summary

Optional body.

Closes #123
```

Examples: `docs(bible): draft assessment section`, `fix(graph): correct prerequisite edge`.

## DCO sign-off

All commits must be signed off under the [Developer Certificate of Origin](https://developercertificate.org/):

```bash
git commit -s -m "docs: fix broken roadmap link"
```

`-s` adds `Signed-off-by: Your Name <email@example.com>` using your Git `user.name` / `user.email`. This certifies you have the right to submit the contribution under the project licenses.

## Pull request rules

- Link the issue: `Closes #N` (or `Fixes #N`) in the PR body.
- Keep PRs **small and focused** — one concern per PR.
- Fill the **PR template** checklist completely.
- **CI must pass** before review/merge.
- At least **one maintainer approval**.
- Address **AI review bot** comments (resolve or reply with rationale).
- We **squash merge** to `main`.

## Issue lifecycle ↔ project Status

| Board Status | Meaning |
| --- | --- |
| **Backlog** | Accepted but not ready (may need design, deps, or `needs-info`) |
| **Ready** | Triaged, prioritized, unblocked — available to claim |
| **In progress** | Assigned and actively worked |
| **In review** | PR open or awaiting maintainer decision |
| **Done** | Merged / shipped / closed as completed |

Issue labels such as `needs-triage`, `blocked`, `needs-info`, `duplicate`, and `wontfix` refine state inside or beside these columns.

## Priority definitions

| Label | Meaning | Response expectation |
| --- | --- | --- |
| `p0-critical` | Outage, security, data loss, or broken main deploy | First response in **1–2 business days** |
| `p1-high` | Major feature gap or serious bug with workaround | Within **~1 week** |
| `p2-medium` | Normal improvements and bugs | Best effort in the current phase |
| `p3-low` | Nice-to-have, polish, deferred ideas | Backlog; no committed SLA |

## Labels

Taxonomy is defined in [`.github/labels.yml`](./.github/labels.yml) and synced across org repos.

| Group | Examples |
| --- | --- |
| **Type** | `bug`, `feature`, `docs`, `content`, `rfc`, `chore`, `refactor`, `test`, `security` |
| **Priority** | `p0-critical` … `p3-low` |
| **Area** | `area:docs`, `area:graph`, `area:content`, `area:learning-experience`, … |
| **Phase** | `phase:0-docs` … `phase:4-global` |
| **Status** | `needs-triage`, `blocked`, `needs-info`, `duplicate`, `wontfix` |
| **Community** | `good first issue`, `help wanted`, `dependencies` |

Issue forms apply the matching **type** label automatically. Triagers add priority, area, and phase.

## Docs and content contributions

Primary repo: [`limitlesslearning/docs`](https://github.com/limitlesslearning/docs) → [live site](https://limitlesslearning.github.io/docs/).

1. Use the **Content proposal** issue form, or open a PR that edits the relevant Markdown under `src/routes/`.
2. Preserve substance; do not invent facts or statistics.
3. Mark open questions as questions — never as locked decisions.
4. Update the [Status](https://limitlesslearning.github.io/docs/status/) page if a section’s draft state changes.
5. For new locked decisions, add a row to the [Decision log](https://limitlesslearning.github.io/docs/decisions/) (do not silently rewrite history).

### Content licensing

| License | Rule |
| --- | --- |
| Code / config | Contributed under **MIT** |
| Docs & educational text we author | Contributed under **CC BY-SA 4.0** |

**Copying external material into the repo or Platform Bible:**

| Allowed to copy (with attribution / share-alike as required) | Link only — do not copy text into our content |
| --- | --- |
| CC BY-SA–compatible works (e.g. **Wikipedia** CC BY-SA) | Non-commercial or incompatible terms (e.g. **MIT OCW**, newer **OpenStax**, **Khan Academy**) |
| **Wikidata** (CC0) | Other All-rights-reserved or unclear licenses |

Additional rules:

- Prefer linking and embedding metadata over copying when in doubt.
- **Khan Academy** material must **not** be used for AI training or scraping; link only where policy allows, and never ingest KA text/media into training sets or bulk scrapers.
- When you adapt CC BY-SA text, keep attribution and share-alike obligations visible in the contribution.

## How decisions are made

1. Open an **RFC / decision proposal** (issue form) or a PR that updates docs.
2. Discuss openly until trade-offs are clear.
3. A maintainer records the outcome in the [Decision log](https://limitlesslearning.github.io/docs/decisions/).
4. **Locked decisions are not reopened** without new evidence; supersede with a new log entry referencing the old `#`.

See [GOVERNANCE.md](./GOVERNANCE.md) for roles and Phase 0 maintainer authority.

## Local development notes

- **docs** — Node.js `>=22.17`, pnpm 10; `pnpm install && pnpm run dev` / `pnpm run build`.
- **platform** — stack planned: SurrealDB · ElysiaJS (Bun) · Tauri · Svelte; follow that repo’s README when it lands.

## Questions

Use [SUPPORT.md](./SUPPORT.md). Security issues: [SECURITY.md](./SECURITY.md) only.
