# One-time auth bootstrap (required before laptop-off nights)

Local Playwright on your PC does **not** carry over to Cursor Cloud. Do this once with the laptop on.

## Goal
Cloud agent can open Naukri + LinkedIn already logged in (or complete login and keep session).

## Steps
1. Open [Cursor Cloud Agents](https://cursor.com/dashboard?tab=cloud-agents) and ensure cloud compute is enabled.
2. Start a **Cloud Agent** on repo `job-apply-agent` (this repo) with prompt:

```text
Open a browser. Go to naukri.com and linkedin.com. If not logged in, pause and ask me to complete login in the cloud browser / provide next steps. Do not store passwords in the repo. After both sites show logged-in home/profile, try opening one Naukri job Apply button and one LinkedIn Easy Apply modal without submitting. Write reports/auth-bootstrap.md with LOGIN_OK or LOGIN_REQUIRED for each site.
```

3. Complete any OTP / captcha yourself in the cloud browser UI when prompted.
4. Confirm `reports/auth-bootstrap.md` shows `LOGIN_OK` for Naukri and LinkedIn.
5. Only then enable the nightly Automation schedule (01:00 IST).

## Fallback (laptop awake only)
If cloud browser auth is unavailable, day batches can still use local Playwright MCP (`user-playwright`) while the laptop is on. Night laptop-off runs stay blocked until cloud login works.

## Security
- Never commit passwords, cookies dumps, or OTP codes into this repo.
- Prefer interactive cloud login over putting secrets in files.
