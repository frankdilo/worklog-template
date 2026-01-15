# CLAUDE.md

Personal work log repository. Daily logs live in `log/YYYY-MM-DD-DayOfWeek.md`, summaries in `log/YYYY-MM-DD-Summary.md`.

## Log Format

Main format:

```markdown
## Worked on today:

Optional context/notes about the day (no bullets)

**Section Name #1**

- Task completed
- Another task with [PR link](url)

**Section Name #2**

- Another task completed
- This is an example
```

Flat list format (when requested):

```markdown
## Worked on today:

- **Project name**: Fixed auth bug in login flow
- Reviewed [PR #456](url) for payment service
- Sync with design team about new dashboard
- Deployed hotfix to production
```

## Adding Entries

- Interpret each message as a work item → add as bullet under appropriate section (`**Bug Fixes**`, `**Features**`, `**Meetings**`, `**Support**`, `**Code review**`, etc.) At start, you can read past log entries (max 10 - do this with a single bash command for speed) to infer other section names and active projects that translate to section names.
- Create sections as needed with `**Section Name**` + blank line after
- Use past tense, include PR links inline naturally
- Fix typos/grammar but **preserve the user's voice, humor, and details**—never strip color or meaning
- When the user shares a link (Linear, GitHub, etc.), infer what it is from the URL slug—don't fetch it
- When looking for recent logs, use `glob log/YYYY-*.md` first to find actual filenames—don't guess the day of week
