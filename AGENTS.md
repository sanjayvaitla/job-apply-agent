# AGENTS.md

## Cursor Cloud specific instructions

### What this repo is
This is **not** a runnable software application. It is a prompt/data workspace that
drives an automated job-application agent for one candidate (Sanjay Vaitla). It
contains only Markdown instructions/data and two resume PDFs — there is **no source
code, no dependency manifest, no build step, and no test suite**.

- Data/config the agent reads: `PROFILE.md` (locked candidate details), `RULES.md`
  (caps, fit filters, skip list, pacing), `applied_log.md` (append-only dedupe
  history), `RESUME.pdf` / `RESUME_campus.pdf` (attachments).
- Agent behavior: `prompts/DAY_AGENT.md`, `prompts/NIGHT_AUTOMATION.md`,
  `automation/cursor-automation.draft.md`.
- Outputs: batch summaries under `reports/`.

### Environment setup
Nothing to install. `git` plus a text editor is the entire dev environment; Python 3
and Node are available on the VM but are not required by the repo. The startup update
script is intentionally a no-op.

### "Lint / test / build" equivalents (no repo tooling exists)
There is no committed linter/test/build. To sanity-check the workspace, run read-only
integrity checks: confirm every file referenced in `README.md` exists, both PDFs start
with `%PDF-`, and `applied_log.md` has no duplicate `company + role` rows (the dedupe
invariant the prompts rely on).

### How the agent actually "runs" — and why it is not run autonomously
The real "run" is a Cursor Cloud Agent + browser/MCP that logs into **Naukri** and
**LinkedIn** using Sanjay's **personal accounts** and submits real job applications
(see `prompts/*` and `AUTH_BOOTSTRAP.md`). Important, non-obvious caveats:

- Submitting an application is an **irreversible real-world action** taken under a real
  person's identity against third-party sites. Do **not** do it autonomously — it
  requires the user's explicit go-ahead for that specific run.
- It needs the user's live Naukri + LinkedIn sessions. Local Playwright cookies do
  **not** carry into cloud VMs (`AUTH_BOOTSTRAP.md`); cloud login is interactive
  (OTP/captcha) and must be completed by the user in the cloud browser.
- Per `PROFILE.md` / `RULES.md`: never invent credentials or experience, never commit
  secrets/cookies/OTPs, always read `applied_log.md` first and skip anything already
  listed, and honor the skip list (unpaid, marketing/sales/content, MedTourEasy clones)
  and caps (pilot 10, then 50).

### Persistence
The agent persists work by appending a row to `applied_log.md` after each successful
apply and writing `reports/YYYY-MM-DD-{night,day}.md`, then committing to the branch.
