## diff-actor

Example configuration

```yaml
name: Differ

on:
  pull_request:
    branches:
      - main
env:
  SHA_AFTER: ${{ github.event.pull_request.head.sha }}
  SHA_BEFORE: ${{ github.event.pull_request.base.sha }}
  AUTHOR_USERNAME: ${{ github.event.pull_request.user.login }}
  REPOSITORY: ${{ github.repository }}
  API_ENDPOINT: ${{ secrets.POST_ENDPOINT }}
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
        uses: konstankinollc/diff-actor@v1.0

        
```
