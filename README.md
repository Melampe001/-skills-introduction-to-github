# -skills-introduction-to-github
https://github.com/Melampe001/skills-introduction-to-github/pull/7

## How to Skip Copilot Scanning

This repository includes a Copilot scan workflow that runs on pull requests. You can skip this scan using one of two methods:

### Method 1: Use the skip-copilot Label
1. Navigate to your pull request on GitHub
2. Click on the "Labels" section on the right sidebar
3. Search for or add the `skip-copilot` label
4. The workflow will be skipped for this PR

### Method 2: Mark PR as Draft
1. Navigate to your pull request on GitHub
2. Click "Convert to draft" in the sidebar or when creating the PR
3. The workflow will not execute while the PR is in draft status (condition: `draft == false`)

### Creating the skip-copilot Label
The `skip-copilot` label is defined in `.github/labels.yml`. To make it available in your repository:
- The label will be automatically created when using label sync tools
- Or manually create it in **Settings → Labels** with:
  - Name: `skip-copilot`
  - Description: "Skip Copilot scanning on this pull request"
  - Color: `#d73a4a` (red)
