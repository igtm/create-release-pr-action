# create-release-pr-action

Github Action composite for [create-release-pr](https://github.com/igtm/create-release-pr)

# example

.github/workspace/example.yaml

```yaml
on: [push]

jobs:
  hello_world_job:
    runs-on: ubuntu-latest
    name: A job to say hello
    steps:
      - uses: actions/checkout@v3
      - id: create release pull request
        uses: igtm/create-release-pr-action@latest
        with:
          base: 'master'
          head: 'staging'
          args: '--no-fetch' # optional
      - run: echo "hello"
        shell: bash
```