# Work Log Template

A lightweight work log system: one markdown file per day, plus optional summaries.

## Structure

- `log/YYYY-MM-DD-DayOfWeek.md` - Daily work logs
- `log/YYYY-MM-DD-Summary.md` - Periodic summaries

## Daily flow

1. Create or open today's log file in `log/`.
2. Add sections using `**Section Name**` and bullet points.
3. Keep entries short and in past tense.

See the sample files in `log/` for the expected format.

## Helper scripts (optional)

- `./open` - Open today's log file (macOS).
- `./edit` - Open today's log file in Sublime Text. Edit this script to use your editor.
- `./copy` - Copy today's log to the clipboard as plain text + RTF (macOS, requires `pandoc`).

## Toggl integration (optional)

The helper script `scripts/wl_hours_worked_toggl.py` pulls time entries from the Toggl Reports API
and formats an `**Hours worked**` block you can append to a daily log or summary.

Set credentials via environment variables or 1Password references:

- `TOGGL_API_TOKEN` or `TOGGL_API_TOKEN_REF`
- `TOGGL_WORKSPACE_ID` or `TOGGL_WORKSPACE_ID_REF`
- Optional: `TOGGL_USER_AGENT`

Example:

```bash
TOGGL_API_TOKEN=your_token TOGGL_WORKSPACE_ID=123456 \
  uv run scripts/wl_hours_worked_toggl.py --since 2025-01-02 --until 2025-01-03
```

## Sample files

- `log/2025-01-02-Thursday.md`
- `log/2025-01-03-Friday.md`
- `log/2025-01-03-Summary.md`
