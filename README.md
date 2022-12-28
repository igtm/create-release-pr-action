# create-release-pr-action


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
      - run: echo "hello"
        shell: bash
```