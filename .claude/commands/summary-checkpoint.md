Generate a summary of work logs since the last summary.

Steps to follow:

1. Find all log files and identify the most recent summary:
   ```bash
   cd log && ls -1 *.md | sort
   ```
   - Summary files end with `-Summary.md`
   - Daily logs follow the pattern `YYYY-MM-DD-DayOfWeek.md`

2. Determine which logs to summarize:
   - If a summary file exists, find all logs created AFTER the most recent summary (lexicographically)
   - If no summary exists, use ALL logs
   - Only include daily log files (not summary files) in the analysis
   - **Exclude today's log file** (the one with today's date) to avoid including partial/in-progress work

3. Read all the identified log files to analyze

4. Generate a concise, high-level summary that:
   - Groups work by **major projects** (e.g., "Social Set Pricing", "AI Chat", "Infrastructure")
   - Focuses ONLY on significant accomplishments and milestones - be selective
   - Each bullet should be high-level (1 line max) - consolidate multiple related tasks into single bullets
   - INCLUDE relevant PR links and URLs from the original logs when they relate to major accomplishments
   - Indicate status when it can be determined from the notes:
     - Add "(shipped)" or "(merged)" for completed work that was deployed/merged
     - Add "(WIP)" for work that's explicitly in progress or incomplete
     - Look for keywords: "merged", "shipped", "deployed", "completed", "WIP", "in progress", "needs testing"
     - Only add status notes when clear from context - omit if uncertain
   - Uses past tense and clear, professional language
   - Aim for 2-5 bullets per major project, not exhaustive lists
   - After major project sections, add an **Other** section with up to 10 minor items (routine work, small fixes, meetings, support issues, misc tasks)

5. Create the summary file:
   - Get today's date: `date +%Y-%m-%d`
   - Filename format: `YYYY-MM-DD-Summary.md`
   - Structure:
     ```markdown
     ## Summary (MM/DD - MM/DD)

     **Project Name**

     - Major accomplishment or milestone (shipped) ([PR #123](url))
     - Another significant task (WIP)

     **Another Project**

     - Key achievements (merged)

     **Other**

     - Minor bug fix or routine task
     - Meeting attended
     - Support issue handled
     ```
   - After the summary content is complete, run `/wl:toggl` with `--since` and `--until` covering the same date range and append the generated `**Hours worked**:` block at the very end of the file. (NOTE: For now, avoid using `/wl:toggl` as it may not have complete data - skip this step if it returns no entries)

6. Confirm to the user:
   - How many log entries were summarized
   - The date range covered
   - The filename created
   - A brief preview of the main projects covered

Important notes:
- Focus on the "big picture" - what projects moved forward and how
- Consolidate related work items (e.g., multiple PRs for the same feature)
- Be concise but informative
- Maintain chronological context by noting the date range
