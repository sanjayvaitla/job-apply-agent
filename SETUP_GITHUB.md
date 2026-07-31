# Push this repo to GitHub (required for Cloud + nightly Automation)

`gh` is not installed on this machine. Cloud Agents need a remote.

## Option A — GitHub website
1. Create a **private** empty repo named `job-apply-agent` on github.com
2. In PowerShell:

```powershell
cd C:\Users\sanja.SANJAY\job-apply-agent
git remote add origin https://github.com/<YOUR_USERNAME>/job-apply-agent.git
git push -u origin master
```

## Option B — Install GitHub CLI
1. Install `gh` from https://cli.github.com/
2. `gh auth login`
3. `cd C:\Users\sanja.SANJAY\job-apply-agent`
4. `gh repo create job-apply-agent --private --source=. --remote=origin --push`

## After push
1. Complete cloud login per AUTH_BOOTSTRAP.md
2. Create the Automation from `automation/cursor-automation.draft.md` in **Agents Window → Automations**
3. Enable schedule only after `reports/auth-bootstrap.md` cloud section is LOGIN_OK
