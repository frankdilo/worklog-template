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

## After you clone

If you want to use this as a fresh repo (without the template git history):

```bash
rm -rf .git
git init
```

Then add your own remote and make your first commit.

## Helper scripts (optional)

- `./open` - Open today's log file (macOS).
- `./edit` - Open today's log file in Sublime Text. Edit this script to use your editor.
- `./copy` - Copy today's log to the clipboard as plain text + RTF (macOS, requires `pandoc`).

## Sample files

- `log/2025-01-02-Thursday.md`
- `log/2025-01-03-Friday.md`
- `log/2025-01-03-Summary.md`
