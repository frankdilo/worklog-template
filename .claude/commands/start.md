Start a daily work logging session.

Steps to follow:

1. Determine today's date:
   - Use a Bash tool call: `date +%Y-%m-%d-%A` to get the filename format (e.g., `2025-10-20-Monday`)

2. Immediately after getting the date, use the Read tool to check if `log/YYYY-MM-DD-DayOfWeek.md` exists:
   - If it exists, you'll see the current contents - proceed to step 3
   - If it doesn't exist (Read returns an error), use the Write tool to create it with:
     ```markdown
     ## Worked on today:

     ```

3. Read logs from the past 2 weeks for context:
   - Use Glob to find all log files: `log/*.md`
   - Filter to logs from the past 14 days based on the date in the filename
   - Read these files to understand:
     - What projects are actively being worked on
     - What section headings are commonly used
     - The formatting patterns and style
   - This context will help maintain consistency when adding new entries

4. Print a recap of the last 2 weeks:
   - Summarize the key accomplishments from the logs you just read
   - Group by project/section where it makes sense
   - Keep it concise but informative (bullet points work well)
   - This helps the user remember what they've been working on

5. Confirm to the user that the daily log session has started and show:
   - The filename being used
   - A brief summary of existing entries (if any)
   - Instructions: "You can now type messages describing completed tasks. Each message will be appended to today's log."

6. After this initial setup, enter "logging mode" where:
   - Follow the guidelines in CLAUDE.md for adding log entries
   - After each append, confirm what was added

7. Stay in logging mode until the user explicitly says "stop logging" or ends the conversation
