# Sanjay job-apply agent (50 night + 50 day)

Cloud-friendly workspace for automated applications.

| File | Purpose |
|------|---------|
| [PROFILE.md](PROFILE.md) | Locked candidate details |
| [RULES.md](RULES.md) | Caps, filters, skip list |
| [applied_log.md](applied_log.md) | Deduped apply history |
| [RESUME.pdf](RESUME.pdf) | Primary resume |
| [prompts/NIGHT_AUTOMATION.md](prompts/NIGHT_AUTOMATION.md) | Overnight Automation instructions |
| [prompts/DAY_AGENT.md](prompts/DAY_AGENT.md) | Daytime Cloud Agent / chat prompt |
| [AUTH_BOOTSTRAP.md](AUTH_BOOTSTRAP.md) | One-time cloud Naukri + LinkedIn login |
| [automation/cursor-automation.draft.md](automation/cursor-automation.draft.md) | Night Automation draft for Cursor UI |
| [reports/](reports/) | Night/day batch reports |

## Daily rhythm
1. **~01:00 IST (laptop off):** Cursor Automation runs night batch (cap 50, pilot 10).
2. **While awake:** paste `prompts/DAY_AGENT.md` into Cloud Agent or chat (cap 50, pilot 10).
3. Check `reports/` and `applied_log.md` each morning/evening.

## Pilot first
First runs use **cap 10**. After two clean pilots, set Automation + day prompts to full **50**.
