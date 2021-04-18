[![Test Siskin download](https://github.com/Oldes/install-siskin/actions/workflows/test.yml/badge.svg)](https://github.com/Oldes/install-siskin/actions/workflows/test.yml)

# Siskin Builder Install Action

This Action can install
    [Siskin-framework Builder](https://github.com/Siskin-framework/Builder)
to a virtual machine of GitHub Actions. 


## Usage

Include this in your workflow:

```yml
 - uses: oldes/install-siskin@v0.3.3
```

These inputs are allowed:

 - `version` -- an available Builder release version (for example: `0.3.3`)
   _Default:_ empty; installs Builder version `0.3.3`.
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
    - uses: actions/checkout@v2
    - uses: oldes/install-siskin@v0.3.3
    - name: Test if Siskin Builder was downloaded
      run: ./siskin
      shell: bash
```
