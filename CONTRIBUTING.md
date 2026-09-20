## Contributing Guidance - v4

This repository is a **personal fork** of [pnp/pnpjs](https://github.com/pnp/pnpjs).

**Prefer contributing upstream** so changes reach npm consumers and the official docs site:

- Official repo: https://github.com/pnp/pnpjs
- Target branch for v4 work: **`version-4`**
- Full guide: [docs/contributing](https://pnp.github.io/pnpjs/contributing/)

---

### Upstream pull requests (recommended)

* Target your pull requests to the **version-4** branch on **pnp/pnpjs**
* Add/update any docs articles related to your changes
* Include a test for any new functionality and ensure all existing tests pass (`npm test`)
  * If you are fixing a bug, include a test that would have caught it
* Ensure lint checks pass (`npm run lint`)
* Keep PRs focused and describe the changes for reviewers
* For larger ideas, [open an issue](https://github.com/pnp/pnpjs/issues) upstream first so maintainers can confirm it is mergeable

### Working in this fork

Useful when experimenting locally before (or without) an upstream PR.

#### Prerequisites

* **Node.js** `>= 18.17.1` (see `engines` in `package.json`)
* Clone this repo and install dependencies: `npm install`

#### Common scripts

| Script | Purpose |
|--------|--------|
| `npm run build` | Production-style build |
| `npm run buildDebug` | Clean + debug build |
| `npm test` | Compile tests and run Mocha |
| `npm run lint` | ESLint on packages and tests |

See [NPM Scripts](https://pnp.github.io/pnpjs/contributing/npm-scripts/) and [Setup Dev Machine](https://pnp.github.io/pnpjs/contributing/setup-dev-machine/) for debugging and local config (`settings.example.js` → local settings).

#### Documentation

* Source: [`docs/`](docs/)
* Build/serve locally with MkDocs using [`mkdocs-requirements.txt`](mkdocs-requirements.txt) and [`mkdocs.yml`](mkdocs.yml)
* Details: [Update Documentation](https://pnp.github.io/pnpjs/contributing/documentation/)

#### Keeping the fork current

```bash
git remote add upstream https://github.com/pnp/pnpjs.git   # once
git fetch upstream
git checkout version-4
git merge upstream/version-4   # or: git reset --hard upstream/version-4 for a hard sync
git push origin version-4
```

GitHub’s **Sync fork** UI works well when you are not rewriting history.

### Questions

* Issues / bugs: https://github.com/pnp/pnpjs/issues
