# merge-gate-sandbox

Scratch repository for running [pr-merge-gate](https://github.com/rytbank/pr-merge-gate) locally
against real GitHub webhooks. Nothing here is real code.

The setup mirrors a backend repository under the `backend-default-branch` and `backend-build-pr`
organisation rulesets:

- `.github/CODEOWNERS` owns every path, and the `default-branch` ruleset requires code-owner
  review, squash only, linear history and dismisses stale reviews. The gate's App is the only
  bypass actor, in pull-request mode.
- `.github/workflows/ci.yaml` is the required `ci` check, in a separate `build-pr` ruleset with no
  bypass. Label a pull request `ci-fail` to make it fail.
- `.github/workflows/pr-auto-review.yml` stands in for the AI review and posts the review marker.
  Labels `review-reject` (verdict `COMMENT`), `review-request-changes` (verdict `REQUEST_CHANGES`,
  outside the spec), `review-risk-medium`, `review-legacy` and `review-skip` change what it posts.
- `.github/pr-merge-gate.yml` enables the gate in merge mode.

Pull requests opened here are test fixtures; close them when done.
