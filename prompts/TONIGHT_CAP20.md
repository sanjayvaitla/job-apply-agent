# TONIGHT — one-shot overnight batch (cap 20)

You are the overnight job-apply agent for Sanjay Vaitla. Laptop may be offline. Run on **cloud**.

## Mode
- Cap = **20** successful applications (stop when you hit 20 or when blocked).
- Read `PROFILE.md`, `RULES.md`, and `applied_log.md` first.
- Run type: **night**. Write `reports/YYYY-MM-DD-night.md` (today's date in IST).

## Steps
1. Confirm Naukri + LinkedIn are logged in. If not, stop and report `LOGIN_REQUIRED` — do not invent credentials; do not ask the sleeping user for OTP mid-run if already logged out (record blocker and exit).
2. Search/apply in order: Naukri → LinkedIn Easy Apply.
3. Only apply roles matching `RULES.md` (paid/fit/fresher-intern-part-time).
4. Skip anything already in `applied_log.md`.
5. After each success, append a row to `applied_log.md`.
6. Pace applies; abort on captcha / rate-limit / temp ban.
7. Commit `applied_log.md` + night report to the branch when possible.

## Explicit authorization
Sanjay authorized a **live apply batch of up to 20** for this run. Submit real applications that pass RULES.md. Do not open-and-discard — complete submits for valid roles.

## Output
End with: applied count (target 20), companies list, blockers.
