# Market Research Dashboard

Automated Reddit market research for my GitHub projects using [reddit-market-research](https://github.com/neonwatty/reddit-market-research).

## How It Works

1. Daily GitHub Actions workflows fetch each repo's README
2. Claude analyzes the project and generates relevant search keywords
3. Searches Reddit for pain points, potential users, and opportunities
4. Saves timestamped findings to `findings/{repo-name}/{date}.md`

## Findings

| Project | Latest |
|---------|--------|
| [seating-arrangement](findings/seating-arrangement/) | AI-powered seating optimization for events |
| [bleep-that-shit](findings/bleep-that-shit/) | Browser-based audio/video word censoring tool |

## Setup

### Required Secrets

Add these secrets to this repo (Settings → Secrets → Actions):

| Secret | Description |
|--------|-------------|
| `REDDIT_CLIENT_ID` | Reddit app client ID |
| `REDDIT_CLIENT_SECRET` | Reddit app client secret |
| `REDDIT_USERNAME` | Reddit username |
| `REDDIT_PASSWORD` | Reddit password |
| `CLAUDE_CODE_OAUTH_TOKEN` | Claude Code OAuth token |

### Adding a New Repo

1. Copy an existing workflow from `.github/workflows/`
2. Update the `TARGET_REPO` and `REPO_NAME` env vars
3. Create `findings/{repo-name}/` directory
4. Optionally adjust the cron schedule

## Manual Trigger

Go to Actions → Select workflow → Run workflow
