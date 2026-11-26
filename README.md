# limitlesslearning/.github

Organization-wide defaults for [Limitless Learning](https://github.com/limitlesslearning): community health files, issue/PR templates, label taxonomy, and reusable workflow templates.

Org profile README: [`profile/README.md`](./profile/README.md) (appears on [github.com/limitlesslearning](https://github.com/limitlesslearning)).

## What lives here

| Path | Purpose |
| --- | --- |
| `profile/README.md` | Organization profile |
| `CONTRIBUTING.md` | Contribution guide (issues, DCO, PRs, labels, content licensing, decisions) |
| `CODE_OF_CONDUCT.md` | Contributor Covenant 2.1 |
| `SECURITY.md` | Private vulnerability reporting |
| `SUPPORT.md` | Where to get help |
| `GOVERNANCE.md` | Phase 0 maintainer model and roles |
| `.github/ISSUE_TEMPLATE/` | Default issue forms + `config.yml` |
| `.github/PULL_REQUEST_TEMPLATE.md` | Default PR checklist |
| `.github/labels.yml` | Labels-as-code taxonomy |
| `.github/workflows/sync-labels.yml` | Syncs labels to `.github`, `docs`, and `platform` ([micnncim/action-label-syncer](https://github.com/micnncim/action-label-syncer)) |
| `workflow-templates/add-to-project.yml` | Copyable workflow to add issues/PRs to [project #1](https://github.com/orgs/limitlesslearning/projects/1) |

Repos inherit these defaults unless a repository provides its own file of the same type.

## Manual setup (maintainers)

### 1. Label sync — `LABEL_SYNC_TOKEN`

Creates/updates/deletes labels in `docs`, `platform`, and this repo from `.github/labels.yml`.

1. Open [Fine-grained personal access tokens](https://github.com/settings/tokens?type=beta) → **Generate new token**.
2. **Resource owner:** `limitlesslearning`.
3. **Repository access:** All repositories (or select `.github`, `docs`, `platform`).
4. **Repository permissions:**
   - **Issues:** Read and write
   - **Metadata:** Read-only
   - **Pull requests:** Read-only
5. Generate the token; copy it once.
6. Org → **Settings → Secrets and variables → Actions → New organization secret**
   - Name: `LABEL_SYNC_TOKEN`
   - Value: the PAT
   - Repository access: at least `.github` (the workflow runs here)

Run **Actions → Sync labels → Run workflow** after the first merge to `main`, or push a change to `labels.yml`.

### 2. Add-to-project — `ADD_TO_PROJECT_TOKEN`

GitHub Free allows one built-in auto-add workflow per project (used by `docs`). Other repos (e.g. `platform`) should use the Action template.

1. Create another fine-grained PAT (or extend the first if you prefer one token for both jobs).
2. **Resource owner:** `limitlesslearning`.
3. **Repository access:** All repositories (or the repos that will run the workflow).
4. **Repository permissions:**
   - **Issues:** Read-only
   - **Metadata:** Read-only
   - **Pull requests:** Read-only
5. **Organization permissions:**
   - **Projects:** Read and write
6. Org secret name: `ADD_TO_PROJECT_TOKEN`
7. In each repo that needs it (start with `platform`):
   - **Add file → Create new file** from the org workflow template **Add to Limitless Learning project**, or copy [`workflow-templates/add-to-project.yml`](./workflow-templates/add-to-project.yml) to `.github/workflows/add-to-project.yml`
   - Ensure the repo can use the org secret (org secret repository access includes that repo)

### 3. Optional hardening

- Enable **private vulnerability reporting** on each public repo (Security settings) so `SECURITY.md` matches product UI.
- Require DCO (e.g. [probot/dco](https://github.com/probot/dco) or a branch rule) so `-s` sign-off is enforced.
- Prefer **squash merge** on application repos to match CONTRIBUTING.

## Related links

- Docs site: [https://limitlesslearning.github.io/docs/](https://limitlesslearning.github.io/docs/)
- Project board: [https://github.com/orgs/limitlesslearning/projects/1](https://github.com/orgs/limitlesslearning/projects/1)
- Licenses: code **MIT**; content **CC BY-SA 4.0**
