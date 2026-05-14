# HEARTBEAT.md - Eric's recurring checks

# Keep this file empty (or with only comments) to skip heartbeat API calls.
# Add tasks below when you want the agent to check something periodically.

## Weekday Morning Brief
Every weekday 7:30 AM (America/New_York):
1. `python3 ~/.openclaw/skills/calendar/calendar_data.py --today` — pull today's events for Eric.
2. `python3 ~/.openclaw/skills/reminder/reminder_data.py --due-today` — pull today's reminders.
3. Alert / report rule: if Eric is in the main session, surface a 3-line brief (next event, next reminder, any kid-logistics conflict). Otherwise stay silent.

[Priority: MEDIUM]
[Last check: 0]

## Sunday Weekly Look-Ahead
Every Sunday 6:00 PM (America/New_York):
1. `python3 ~/.openclaw/skills/calendar/calendar_data.py --week-ahead` — pull next week's calendar.
2. `python3 ~/.openclaw/skills/email/email_data.py --unread --from "Orlando City Youth" --from "Banfield" --from "Brightpath"` — surface only logistics emails Eric likely owes a reply on.
3. Alert / report rule: surface to Eric only if there is a scheduling conflict, a registration deadline within 7 days, or an unanswered email older than 5 days. Otherwise stay silent.

[Priority: LOW]
[Last check: 0]
