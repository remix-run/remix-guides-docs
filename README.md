# Remix Guides

This repository builds and deploys the [Remix](https://github.com/remix-run/remix) guides to GitHub Pages. The guide source and static-site generator live in the Remix monorepo under [`guides/`](https://github.com/remix-run/remix/tree/brooks/guides-markdown-chapters/guides).

## Deployment

[`.github/workflows/deploy.yml`](.github/workflows/deploy.yml) checks out the Remix monorepo, prerenders the guides, and deploys the generated site as a GitHub Pages artifact.

Deployments run when:

- A commit is pushed to this repository's `main` branch.
- The **Deploy Remix Guides** workflow is run manually. Its `ref` input accepts a Remix branch, tag, or commit.
- This repository receives an `update-guides` repository dispatch. The optional `ref` client payload selects the Remix source ref.

Until the guides PR merges, deployments default to `brooks/guides-markdown-chapters`. After it merges, the workflow default should be changed to `main`.
