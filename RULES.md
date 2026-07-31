# Job apply rules (50 night + 50 day)

## Caps
| Run | Cap | Report file |
|-----|-----|-------------|
| Night (scheduled Automation, laptop off) | **50** | `reports/YYYY-MM-DD-night.md` |
| Day (Cloud Agent / chat while awake) | **50** | `reports/YYYY-MM-DD-day.md` |
| **Pilot mode** (first runs only) | **10** each | same paths; set `PILOT=true` in prompt |

Stop early if platform shows captcha, “too many applications”, temporary blocks, or login failure.

## Fit filters (must pass)
- Roles: Python, AI/ML, SQL, data analyst/scientist, full-stack, software engineer **intern / fresher / trainee / junior / part-time**
- Experience: prefer 0–2 YOE; skip roles requiring **5+ YOE** or senior/lead/manager
- Pay: **paid or stipend**. Skip if job text says **unpaid**
- Locations: Bengaluru / Bangalore, Hyderabad, remote India
- Employment: full-time fresher, internship, trainee, **paid part-time**

## Platforms (priority order)
1. **Naukri** — 1-click Apply when available
2. **LinkedIn** — Easy Apply only (`/jobs/view/{id}/apply/` when helpful)
3. **Foundit** — only if already logged in
4. **Internshala** — **SKIP** (account on hold)

## Skip always
- Unpaid internships
- Marketing, content, sales, video editing, Instagram growth
- MedTourEasy city-clone spam (Dwarka/UAE/Bhopal/etc. duplicates after one apply)
- Already listed in `applied_log.md` (match company + role title)
- Company-site-only flows that need multi-page accounts unless clearly quick
- Roles that demand payment from the candidate

## Quality preference
- Prefer known / product companies when available (e.g. Red Hat, Wabtec class)
- Still allow smaller genuine product or engineering firms if paid + skill fit
- Skip vague “walk-in only fresher” spam with no company clarity when better options exist

## Pacing
- Short pause between submits (~15–45s)
- Max ~25–40 aggressive bursts then cool down if warnings appear
- Never force-submit through security checks

## After each successful apply
Append one line to `applied_log.md`:

```text
| YYYY-MM-DD | Company | Role | Platform | full-time\|part-time\|internship | notes |
```

## Report format (`reports/…`)
1. Date + run type (night/day) + pilot or full
2. Applied count / cap
3. Table of companies applied
4. Skipped + why (sample)
5. Blocks / captcha / login issues
6. Remaining quota for the other half of the day
