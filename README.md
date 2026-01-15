# Work Log Template

A lightweight work log system: one markdown file per day, plus optional summaries.

## Structure

- `log/YYYY-MM-DD-DayOfWeek.md` - Daily work logs
- `log/YYYY-MM-DD-Summary.md` - Periodic summaries

## Daily flow

1. Run Claude Code in this repo.
2. Type `/start`.
3. Start writing what you are doing in the chat; logs will populate automatically.
4. (Optional) Open today's log file in `log/` to review or edit.
5. Add sections using `**Section Name**` and bullet points.
6. Keep entries short and in past tense.

See the sample files in `log/` for the expected format.

## Claude commands

This repo includes custom Claude commands in `.claude/commands`:

- `/start` - Start a work log session.
- `/summary-checkpoint` - Capture a checkpoint summary.
- `/preview` - Preview the current log output.
- `/polish` - Clean up wording and formatting.

## Create a new repo from this template

Use GitHub's "Use this template" button on the repo page, or run:

```bash
gh repo create your-repo-name --template frankdilo/worklog-template --private
```

Then clone your new repo and start logging.

## Helper scripts (optional)

- `./open` - Open today's log file (macOS).
- `./edit` - Open today's log file in Sublime Text. Edit this script to use your editor.
- `./copy` - Copy today's log to the clipboard as plain text + RTF (macOS, requires `pandoc`).

## Sample files

- `log/2025-01-02-Thursday.md`
- `log/2025-01-03-Friday.md`
- `log/2025-01-03-Summary.md`
