Display a preview of today's work log.

Steps to follow:

1. Get today's date using Bash:
   ```bash
   date +%Y-%m-%d-%A
   ```

2. Construct the log file path: `log/YYYY-MM-DD-DayOfWeek.md`

3. Use the Read tool to read the file:
   - If the file exists, display its contents to the user as a preview
   - If the file doesn't exist, inform the user that no log exists yet for today

4. Format the output clearly for the user:
   - Show the filename
   - Display the contents of the log file with links simplified: convert markdown links like `([PR #123](url))` to just `[PR #123]` for better readability
   - If no log exists, suggest using `/wl:start` to create one
