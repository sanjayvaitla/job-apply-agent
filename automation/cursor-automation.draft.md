# Cursor Automation draft — Night Job Applies

Use this to create a **new** Cursor Automation (Agents Window → Automations). Prefill is not available from this chat session; copy these values into the editor.

## Draft table

| Draft field | Value |
|-------------|--------|
| Name | Night Job Applies (Sanjay) |
| Description | Daily cloud batch: up to 50 paid/fit Naukri + LinkedIn Easy Apply roles while laptop is off; updates applied_log and writes a night report. |
| Trigger | Schedule — every day at **01:00** (set timezone to IST / Asia/Kolkata in the editor if shown). Cron equivalent if UTC-only: `30 19 * * *` (01:00 IST = 19:30 UTC). Prefer editor “01:00 Asia/Kolkata” if available. |
| Tools | Cloud agent + browser / MCP as configured in Cloud Agents dashboard for LinkedIn & Naukri. Do not rely on local Playwright. |
| Instructions | Follow `prompts/NIGHT_AUTOMATION.md` in this repo. First week: **PILOT cap 10**. Then raise to **50**. Read PROFILE.md, RULES.md, applied_log.md. Write reports/YYYY-MM-DD-night.md. |
| Resolved settings | Repo: this `job-apply-agent` GitHub repo · Branch: `main` (or default) · Schedule: daily 01:00 IST · Cap: pilot 10 → then 50 |
| To finish in editor | (1) Select this GitHub repo + branch (2) Confirm cron/timezone (3) Attach cloud browser / MCP for job sites (4) Enable after AUTH_BOOTSTRAP LOGIN_OK |

## Agent instructions (paste into Automation prompt)

```text
PILOT MODE: cap 10 until two successful nights, then cap 50.

Follow prompts/NIGHT_AUTOMATION.md, PROFILE.md, and RULES.md in the job-apply-agent repo.
Apply only paid, fit fresher/intern/part-time tech roles on Naukri then LinkedIn Easy Apply.
Skip unpaid, marketing, MedTourEasy clones, and anything already in applied_log.md.
Update applied_log.md after each success. Write reports/YYYY-MM-DD-night.md.
If Naukri or LinkedIn is not logged in, stop and report LOGIN_REQUIRED. Never commit secrets.
```

## Enable order
1. Complete [AUTH_BOOTSTRAP.md](../AUTH_BOOTSTRAP.md)
2. Push this repo to GitHub (private OK)
3. Create Automation with the table above
4. Run once manually (pilot 10) before trusting the nightly schedule
