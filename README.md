# GitHub Stats Visualization

<a href="https://github.com/chrisjonesonline/github-stats">
<img src="https://raw.githubusercontent.com/chrisjonesonline/github-stats/master/generated/overview.svg#gh-dark-mode-only" alt="GitHub stats overview" />
<img src="https://raw.githubusercontent.com/chrisjonesonline/github-stats/master/generated/languages.svg#gh-dark-mode-only" alt="Most used languages" />
<img src="https://raw.githubusercontent.com/chrisjonesonline/github-stats/master/generated/overview.svg#gh-light-mode-only" alt="GitHub stats overview" />
<img src="https://raw.githubusercontent.com/chrisjonesonline/github-stats/master/generated/languages.svg#gh-light-mode-only" alt="Most used languages" />
</a>

Generate visualizations of GitHub user and repository statistics with GitHub Actions. Visualizations can include data from both public and private repositories, as well as repositories you have contributed to but do not own.

Generated images automatically switch between GitHub light and dark themes.

## Features

- GitHub profile statistics
- Most-used language visualization
- Public and private repository support
- GitHub Actions automation
- Automatic daily updates
- Manual workflow refresh
- Light and dark theme support
- Repository and language exclusions
- Optional exclusion of forked repositories
- No external stats server required

## How It Works

This project collects profile and repository statistics using the GitHub API and generates SVG images that can be embedded in a GitHub profile README or other Markdown files.

Because the statistics are generated through GitHub Actions using your own personal access token, private repository activity can be included without exposing the private repositories themselves.

Generated files are stored in:

```text
generated/overview.svg
generated/languages.svg
