# Setup Yorick

![GitHub release](https://img.shields.io/github/v/release/fabasoad/setup-yorick-action?include_prereleases)
![Functional Tests](https://github.com/fabasoad/setup-yorick-action/workflows/Functional%20Tests/badge.svg)
[![pre-commit.ci status](https://results.pre-commit.ci/badge/github/fabasoad/setup-yorick-action/main.svg)](https://results.pre-commit.ci/latest/github/fabasoad/setup-yorick-action/main)

This action installs a [Yorick](https://yorick.sourceforge.net).

## Prerequisites

The following tools have to be installed for successful work of this GitHub action:
[bash](https://www.gnu.org/software/bash), [git](https://git-scm.com), [cmake](https://cmake.org),
[make](https://www.gnu.org/software/make/manual/make.html).

## Inputs

| Name    | Required | Description                                                                  | Default    | Possible values              |
|---------|----------|------------------------------------------------------------------------------|------------|------------------------------|
| version | No       | Yorick version that can be found [here](https://github.com/LLNL/yorick/tags) | `y_2_2_04` | `Y_2_2_03`, `y_2_2_02`, etc. |

## Example usage

### Workflow configuration

```yaml
name: Test

on: push

jobs:
  setup:
    name: yorick
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@main
      - uses: fabasoad/setup-yorick-action@main
        with:
          version: y_2_2_04
      - name: Print version
        run: yorick -v
```

### Result

```shell
Run yorick -v
yorick version: 3.4
```