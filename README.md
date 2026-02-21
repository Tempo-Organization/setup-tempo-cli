# setup-tempo-cli

example usage yml
```
name: make_mod_releases

on:
  push:
    branches:
      - main
  workflow_dispatch:

jobs:
  make_mod_releases:
    name: make_mod_releases
    runs-on: [self-hosted, windows, x64]

    steps:
      - name: Checkout
        uses: actions/checkout@v6

      - name: Setup tempo-cli
        uses: Tempo-Organization/setup-tempo-cli@v1.1

      - name: Run tempo-cli mod release creation command
        run: tempo_cli run full_run_all --settings_json ".tempo.json"
```
