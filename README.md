# Rerun Cancelled Workflows Action
Used to rerun workflows based on the conclusion of the workflow (e.g. cancelled workflows). This can be used to resolve issues such as [GitHub cancelling workflow runs that are pending](https://github.com/orgs/community/discussions/5435).

## Example Workflow
```
name: Rerun Cancelled Workflows
on:
  workflow_dispatch:
  schedule:
    - cron: '*/20 6-20 * * *'

jobs:
  rerun-workflows:
    name: Rerun Cancelled Workflows
    runs-on: ubuntu-latest
    steps:
      - name: Rerun Cancelled Workflows
        uses: synergy-au/rerun-workflows-action@v1
        with:
          auth-token: ${{ secrets.GITHUB_TOKEN }}
```