# create-release-pr-action

Github Action composite for [create-release-pr](https://github.com/igtm/create-release-pr)

# example

.github/workflows/create-release-pr-master.yaml

```yaml
name: Create PullRequest from staging to master
on:
  push:
    branches:
      - staging

jobs:
  create_release_pr_job:
    runs-on: ubuntu-latest
    name: create-release-pr
    steps:
      - uses: actions/checkout@v3
        with:
          fetch-depth: 0
      - uses: igtm/create-release-pr-action@v0.0.4
        with:
          base: "master"
          head: "staging"
          args: "--no-fetch" # optional
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
```
