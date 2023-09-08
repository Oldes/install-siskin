[![Test Siskin download](https://github.com/Oldes/install-siskin/actions/workflows/test.yml/badge.svg)](https://github.com/Oldes/install-siskin/actions/workflows/test.yml)

# Siskin Builder Install Action

This Action can install
    [Siskin-framework Builder](https://github.com/Siskin-framework/Builder)
to a virtual machine of GitHub Actions. 


## Usage

Include this in your workflow:

```yml
 - uses: oldes/install-siskin@v0.13.0
```

These inputs are allowed:

 - `version` -- an available Builder release version (for example: `0.13.0`)
   _Default:_ empty; installs Builder version `0.13.0`.
 - `name` -- an optional local file name
   _Default:_ empty; used name `siskin`.

### Working Example

```yml
name: Siskin Demo

on:
  push:
    branches:
      - master

jobs:
  build:
    runs-on: ${{ matrix.os }}
    strategy:
      matrix:
        os: ["ubuntu-latest", "windows-latest", "macos-latest"]
    steps:
    - uses: actions/checkout@v3
    - uses: oldes/install-siskin@v0.13.0
    - name: Test if Siskin Builder was downloaded
      run: ./siskin --help
      shell: bash
```

Real life usage example can be seen for example at this [Build Rebol workflow](https://github.com/Siskin-framework/Rebol/actions/runs/760323990/workflow).
