# playclaude

Claude Code GitHub Actions integration for automated code review and interactive AI assistance on issues and pull requests.

## Workflows

### Claude Code (`claude.yml`)

Responds to `@claude` mentions in:

- Issue comments
- Pull request review comments
- Pull request reviews
- New or assigned issues

When triggered, Claude reads the repository context and performs the instructions from the comment or issue that tagged it.

### Claude Code Review (`claude-code-review.yml`)

Runs automatically on pull requests (opened, updated, ready for review, reopened). Uses the `code-review` plugin to generate AI-powered code review feedback.

## Setup

1. **Add the OAuth token** — Go to **Settings > Secrets and variables > Actions** and create a repository secret named `CLAUDE_CODE_OAUTH_TOKEN` with your Claude Code OAuth token.

2. **Enable workflows** — The workflows in `.github/workflows/` are ready to use once the secret is configured.

## Usage

- **Interactive:** Mention `@claude` in any issue or PR comment to get AI assistance.
- **Code review:** Open a pull request and the review workflow runs automatically.

## Customization

Both workflows support optional configuration via commented-out sections:

- **`claude.yml`** — Custom prompts (`prompt`), tool restrictions (`claude_args`), and additional permissions.
- **`claude-code-review.yml`** — File path filters (`paths`), PR author filters (`if` condition).

See the [claude-code-action docs](https://github.com/anthropics/claude-code-action/blob/main/docs/usage.md) for all available options.
