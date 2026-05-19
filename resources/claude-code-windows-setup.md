# Claude Code Workshop — Windows Setup Handoff

This guide takes a fresh Windows machine to a working Claude Code environment with the
workshop repo cloned and open in VS Code. Run everything in **PowerShell** (your prompt
should start with `PS`). You do **not** need to run as Administrator.

Estimated time: 15–25 minutes, mostly waiting on downloads.

---

## Before you start

- You need a **paid Claude account** (Pro, Max, Team, or Enterprise). The free plan does
  not include Claude Code.
- `winget` is built into Windows 11 and modern Windows 10. Confirm it works:
  ```powershell
  winget --version
  ```
  If that errors, install "App Installer" from the Microsoft Store, then reopen PowerShell.

---

## Step 1 — Install the core tools with winget

Run these four commands one at a time. Each downloads and installs silently.

```powershell
winget install --id Git.Git -e
winget install --id OpenJS.NodeJS -e
winget install --id Microsoft.VisualStudioCode -e
winget install --id Python.Python.3.13 -e
```

Notes:
- `-e` forces an exact match on the package ID so you get the right package.
- If winget says a package is **already installed**, that's fine — skip it.
- If it asks you to accept source agreements, type `Y`.
- The Git installer's defaults are correct for this workshop — in particular it adds Git
  to your PATH, which Claude Code needs.

When all four finish, **close PowerShell completely and open a fresh window.** This is
required — installers update your PATH, and an already-open terminal won't see the change.

---

## Step 2 — Verify the core tools

In the new PowerShell window:

```powershell
git --version
node --version
npm --version
python --version
code --version
```

You should get a version number from each. Two common snags:

- **`python` opens the Microsoft Store or says "Python was not found":** the Store stub is
  shadowing the real install. Go to **Settings → Apps → Advanced app settings → App
  execution aliases** and turn **off** the toggles for `python.exe` and `python3.exe`,
  then reopen PowerShell.
- **`code` is not recognized:** reopen PowerShell once more; if it still fails, open VS
  Code manually, press `Ctrl+Shift+P`, and run **"Shell Command: Install 'code' command
  in PATH"**.

---

## Step 3 — Install the Claude Code CLI

Run the official native installer in PowerShell:

```powershell
irm https://claude.ai/install.ps1 | iex
```

This installs the `claude` binary to `C:\Users\<your-username>\.local\bin`. No Node.js is
required for Claude Code itself.

When it finishes, **close PowerShell and open a fresh window**, then check:

```powershell
claude --version
```

### If you get "claude is not recognized"

This is a known issue — the installer sometimes doesn't add its folder to your PATH.
Fix it (replace `learn` with your actual Windows username if different):

```powershell
$new = "$env:USERPROFILE\.local\bin"
$current = [Environment]::GetEnvironmentVariable("Path", "User")
[Environment]::SetEnvironmentVariable("Path", "$current;$new", "User")
```

Then **fully close every PowerShell window**, open a new one, and try `claude --version`
again. Once it works, run a quick health check:

```powershell
claude doctor
```

---

## Step 4 — Create the workspace folder and clone the repo

In PowerShell:

```powershell
cd $env:USERPROFILE\Development
mkdir claude-code
cd claude-code
git clone https://github.com/bok-learning-lab/claude-code-20260519.git
```

Adjust the first line if your projects live somewhere else. The repo is public, so cloning
needs no login. It clones into a subfolder named `claude-code-20260519`.

---

## Step 5 — Open the project in VS Code

```powershell
cd claude-code-20260519
code .
```

VS Code opens with the project loaded. If it asks **"Do you trust the authors of the
files in this folder?"**, choose **Yes, I trust the authors** — otherwise some features
stay disabled.

---

## Step 6 — Log in to Claude in the integrated terminal

1. In VS Code, open the integrated terminal: **Terminal → New Terminal**
   (or `` Ctrl+` ``).
2. Confirm you're at the project root — the prompt should end in
   `...\claude-code\claude-code-20260519`.
3. Start Claude Code:
   ```powershell
   claude
   ```
4. On first run it walks you through login. Choose your account option and a browser
   window opens for sign-in. Log in with your paid Claude account and approve the
   request. The browser will say you can return to the terminal.
5. Back in the terminal, Claude Code is ready. Type a message to confirm it responds,
   e.g. *"What files are in this project?"*

To exit Claude Code, type `/exit` or press `Ctrl+C` twice.

---

## Quick reference

| Goal | Command |
|------|---------|
| Check a tool is installed | `git --version`, `node --version`, etc. |
| See where a command lives | `Get-Command claude` (PowerShell's `which`) |
| Claude Code health check | `claude doctor` |
| Update Claude Code | auto-updates in the background |
| Update winget packages | `winget upgrade --all` |
| Start Claude Code | `claude` (from the project folder) |
| Exit Claude Code | `/exit` |

---

## Troubleshooting

- **A command "is not recognized" right after installing it** — almost always a stale
  PATH. Close every terminal window and open a fresh one.
- **`claude` still not found after the PATH fix** — confirm the binary exists with
  `Test-Path "$env:USERPROFILE\.local\bin\claude.exe"`. If `True`, you have a stale
  terminal; if `False`, re-run the Step 3 installer.
- **Browser login gets stuck in a loop** — try a different browser for the initial
  sign-in, or temporarily relax strict tracker/cookie blocking.
- **Claude Code can't find Git Bash** — make sure Step 1's Git install completed; Claude
  Code falls back to PowerShell without it, which works but is less smooth.