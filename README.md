# merge-gate-sandbox

Scratch repository for running [pr-merge-gate](https://github.com/rytbank/pr-merge-gate) locally
against real GitHub webhooks. Nothing here is real code.

- `.github/pr-merge-gate.yml` enables the gate in dry-run mode.
- `.github/workflows/ci.yaml` runs a trivial `ci` check on every pull request, so a ruleset can
  require it.

Pull requests opened here are test fixtures; close them when done.
