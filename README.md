## diff-actor

Make sure you have the following secrets configured for the project:

```bash
API_ENDPOINT
API_KEY
```

Example configuration

```yaml
name: Differ

on:
  pull_request:
    branches:
      - main
env:
  API_ENDPOINT: ${{ secrets.API_ENDPOINT }}
  API_KEY: ${{ secrets.API_KEY }}

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - name: checkout
        uses: actions/checkout@v2
        with:
          fetch-depth: 0
      - name: konstankino-diff-actor
        uses: konstankinollc/diff-actor@main

        
```
