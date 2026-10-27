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
```

## Setup

### 1. Create a Personal Access Token

Create a GitHub Personal Access Token with the following permissions:

```text
repo
read:user
```

Copy the token when it is generated.

> Never commit your personal access token directly to the repository.

### 2. Add the Repository Secret

Go to:

```text
Settings → Secrets and variables → Actions
```

Create a repository secret named:

```text
ACCESS_TOKEN
```

Paste your Personal Access Token as the secret value.

## Optional Configuration

Additional repository secrets can be used to customize the generated statistics.

### Exclude Repositories

Create a secret named:

```text
EXCLUDED
```

Add repositories using the following format:

```text
owner/repository,owner/repository
```

### Exclude Languages

Create a secret named:

```text
EXCLUDED_LANGS
```

For example:

```text
html,tex
```

### Exclude Forked Repositories

The workflow supports:

```yaml
EXCLUDE_FORKED_REPOS: true
```

This limits statistics to owned repositories rather than including contributed forks.

## Generate Stats

Statistics are generated automatically every 24 hours through GitHub Actions.

To manually regenerate them:

1. Open the **Actions** tab.
2. Select **Generate Stats Images**.
3. Click **Run workflow**.
4. Wait for the workflow to complete.

Updated SVG files will be committed to the `generated` directory when the statistics change.

## Add Stats to Your Profile

Add the following to your GitHub profile README, replacing `username` with your GitHub username.

### Overview

```md
![](https://raw.githubusercontent.com/username/github-stats/master/generated/overview.svg#gh-dark-mode-only)
![](https://raw.githubusercontent.com/username/github-stats/master/generated/overview.svg#gh-light-mode-only)
```

### Languages

```md
![](https://raw.githubusercontent.com/username/github-stats/master/generated/languages.svg#gh-dark-mode-only)
![](https://raw.githubusercontent.com/username/github-stats/master/generated/languages.svg#gh-light-mode-only)
```

### Example

```md
![](https://raw.githubusercontent.com/chrisjonesonline/github-stats/master/generated/overview.svg#gh-dark-mode-only)
![](https://raw.githubusercontent.com/chrisjonesonline/github-stats/master/generated/overview.svg#gh-light-mode-only)

![](https://raw.githubusercontent.com/chrisjonesonline/github-stats/master/generated/languages.svg#gh-dark-mode-only)
![](https://raw.githubusercontent.com/chrisjonesonline/github-stats/master/generated/languages.svg#gh-light-mode-only)
```

## Privacy

Private repository statistics can be included when `ACCESS_TOKEN` has sufficient permissions.

The generated SVGs contain aggregate statistics. However, errors produced while querying private repositories may expose repository names in publicly visible GitHub Actions logs.

If private repository names are sensitive, review workflow visibility and logs accordingly.

## Requirements

- GitHub account
- Personal Access Token
- GitHub Actions enabled
- `repo` and `read:user` token permissions

## Credits

Based on `jstrieb/github-stats`.

## License

See the repository's license file for licensing information.
