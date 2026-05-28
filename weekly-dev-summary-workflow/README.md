# Weekly Dev Summary Workflow

Importable n8n workflow that generates a weekly narrative summary for a GitHub repository with Claude and posts it to a Discord webhook.

## Setup

1. Import `workflow.json` into n8n.
2. Set these n8n environment variables: `GITHUB_OWNER`, `GITHUB_REPO`, `GITHUB_TOKEN`, `ANTHROPIC_API_KEY`, `SUMMARY_DESTINATION_WEBHOOK_URL`, and `SUMMARY_LANGUAGE` (`EN` or `FR`).
3. Open the workflow and confirm the `Weekly Friday 5pm` schedule matches your n8n instance timezone.
4. Run the workflow manually once, then confirm the Discord channel receives the generated summary.
5. Activate the workflow.

## What It Does

- Runs weekly on Friday at 5pm.
- Fetches the last 7 days of commits, closed issues, and merged pull requests from the GitHub API.
- Calls Claude with `claude-sonnet-4-20250514` to produce a concise narrative summary.
- Posts the Markdown summary to Discord using `SUMMARY_DESTINATION_WEBHOOK_URL`.
- Supports English and French through `SUMMARY_LANGUAGE`.

## Successful Execution Screenshot

After a live n8n run with your own non-committed credentials, add a sanitized screenshot at:

```text
weekly-dev-summary-workflow/screenshots/successful-execution.png
```

Keep API keys, webhook URLs, private repository names, account names, and personal data out of the screenshot.

## Local Validation

```bash
bash weekly-dev-summary-workflow/validate.sh
```

