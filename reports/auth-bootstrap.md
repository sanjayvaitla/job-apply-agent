# Auth bootstrap report — 2026-08-01

## Local Playwright (laptop on) — verified 2026-08-01
| Site | Status | Evidence |
|------|--------|----------|
| Naukri | **LOGIN_OK** | `https://www.naukri.com/mnjuser/homepage` loaded as fresher home (logged in) |
| LinkedIn | **LOGIN_OK** | `https://www.linkedin.com/feed/` loaded (not login wall) |
| Foundit | Session present (dashboard tab) | Optional for v1 |
| Internshala | SKIP | Account on hold |

## Cloud (laptop off) — blocked until GitHub remote exists
| Site | Status | Action |
|------|--------|--------|
| Naukri | **LOGIN_REQUIRED** | No cloud remote yet — see SETUP_GITHUB.md then AUTH_BOOTSTRAP.md |
| LinkedIn | **LOGIN_REQUIRED** | Same — Cloud Agent launch failed: 0 git remotes on parent workspace |

## Blocker for nightly Automation
Night runs stay **disabled** until cloud shows LOGIN_OK for Naukri + LinkedIn.

## Day path (works now)
While laptop is on, day pilot / day batch can use local `user-playwright` with the verified sessions above.
