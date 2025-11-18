name: Copilot Security Agent

on:
  pull_request:
    types: [opened, synchronize, labeled, unlabeled]

permissions:
  contents: read
  security-events: write
  actions: read

jobs:
  copilot-security:
    if: github.event.pull_request.draft == false && !contains(join(github.event.pull_request.labels.*.name, ','), 'skip-copilot')
    runs-on: ubuntu-latest

    steps:
      - name: Checkout
        uses: actions/checkout@v4

      - name: Security Scan (Copilot Security Agent)
        uses: github/copilot-security@v1
        with:
          github-token: ${{ secrets.GITHUB_TOKEN }}# -skills-introduction-to-github
https://github.com/Melampe001/skills-introduction-to-github/pull/7
