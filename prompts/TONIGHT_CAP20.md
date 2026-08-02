# Tonight batch — LIVE apply, cap 20 (laptop off)

One-off overnight batch authorized by Sanjay. Run on **cloud**. Target: **at least 20 successful applications**.

## Mode
- Read `PROFILE.md`, `RULES.md`, and `applied_log.md` first.
- Cap = **20** successful applies (this run).
- Run type: **night**. Write `reports/YYYY-MM-DD-night.md` (IST date). If a night report already exists for today, write a distinct file (e.g. `-night-cap20.md`) so earlier reports are not overwritten.

## Steps
1. Confirm Naukri + LinkedIn are logged in. If not, STOP and report `LOGIN_REQUIRED` — never invent credentials.
2. Apply in order: Naukri (1-click / apply) → LinkedIn Easy Apply. Foundit only if already logged in.
3. Apply ONLY to roles passing `RULES.md`: paid, fresher/intern/trainee/junior (0-2 YOE), Python/AI/ML/SQL/data/full-stack/SWE/backend, in Bengaluru/Hyderabad/remote India.
4. Skip unpaid, marketing/content/sales/video/Instagram, MedTourEasy clones, senior/5+ YOE, external multi-page company-site flows, and anything already in `applied_log.md` (dedupe on company + role).
5. Use `PROFILE.md` form defaults; never invent experience. Attach `RESUME.pdf` when a file upload is offered.
6. Pace ~15-45s between submits. STOP on captcha, "too many applications", security checkpoint, or rate-limit.
7. Append one row to `applied_log.md` after each genuine success. Commit log + report; never commit secrets.

## Operational note (automation harness)
Run in **bounded batches** (~5 applies per browser sub-session) using fresh browser sessions, because a single long GUI session can exceed the model's per-request image limit. Only count applications that show an explicit success confirmation.

## Output
End with: successful count / 20, company list, notable skips, and any blocks.
