# Claude Code Setup Guide

**Copy this entire document into ChatGPT, Claude, or Cursor's AI chat to get guided help with setup.**

---

## FOR AI ASSISTANTS

You are helping a user set up Claude Code in Cursor IDE. Follow this protocol:

**STEP 1 - Determine their situation:**
1. What operating system? (Windows or Mac)
2. What's already installed? Have them run the prerequisite checks below
3. Do they have Claude Pro subscription ($20/month)?

**STEP 2 - Guide them through ONLY the steps they need:**
- Skip to the relevant platform section (Windows or Mac)
- Skip installation steps for tools they already have
- Use the "Common Steps" section once platform-specific setup is done

**STEP 3 - Watch for these common issues:**
- **Invisible password**: ALWAYS warn before any password prompt
- **Terminal restart needed**: After ANY install, terminal must be closed/reopened
- **"command not found"**: Usually means terminal restart needed
- **Claude auth fails**: Usually wrong subscription tier (need Pro, not Free)

---

## Quick Start: What's Your Situation?

**Tell your AI assistant:**
1. **What computer?** Windows or Mac?
2. **Run these checks** in a terminal and share results:
   ```
   git --version
   gh --version
   ```
3. **Do you have Claude Pro?** ($20/month at claude.ai, NOT free tier)

---

## Prerequisite Check Table

Run each command. If it shows a version number, you can skip that installation step.

| Command | Example Success Output | If Missing, Install |
|---------|----------------------|---------------------|
| `git --version` | `git version 2.39.0` | Git (Step 2) |
| `gh --version` | `gh version 2.40.1` | GitHub CLI (Step 3-4) |
| `brew --version` (Mac only) | `Homebrew 4.1.0` | Homebrew (Mac Step 2) |

---

## ⚠️ CRITICAL: Two Things That Confuse Everyone

### 1. Invisible Password Typing

When the terminal asks for your password:
- **YOUR TYPING WILL NOT SHOW ON SCREEN**
- No dots, no asterisks, no cursor movement - NOTHING
- This is normal security behavior, not a bug
- **Just type your password and press Enter**

This trips up almost everyone. The password IS being entered even though you see nothing.

### 2. Terminal Restart Rule

After installing ANY tool (Git, GitHub CLI, Homebrew):
1. Type `exit` and press Enter
2. Close the terminal panel
3. Open a NEW terminal (Terminal → New Terminal)

The new terminal "sees" newly installed tools. The old one doesn't.

---

## Prerequisites

Before starting, you need:

- [ ] **Admin access** to your computer (can install software)
- [ ] **GitHub account** - create free at github.com if needed
- [ ] **Claude Pro subscription** - $20/month at claude.ai
  - Free tier does NOT work with Claude Code
  - Team accounts need "Standard" or "Premium" seat (not "Basic")
- [ ] **Stable internet**

---

## What's Your Platform?

**Skip to the section for your operating system:**

- **Windows** → Jump to "Windows Setup" section
- **Mac** → Jump to "Mac Setup" section

---

# Windows Setup

Windows setup is straightforward - just download installers and run them.

## Step 1: Install Cursor IDE or VSCode

1. Go to https://www.cursor.com or https://code.visualstudio.com/download
2. Download the Windows installer (.exe)
3. Run the installer, click through prompts
4. Launch Cursor or VSCode from Start menu
5. Create a Cursor account (free) when prompted (if using Cursor)
**Verify:** Cursor or VSCode opens with welcome screen, you see File menu at top

---

## Step 2: Install Git for Windows

1. Go to https://git-scm.com/download/win
2. Download the installer
3. Run installer - **use all default options** (just keep clicking Next)
4. Finish installation

**Do NOT open Cursor yet if it's open - close it first**

---

## Step 3: Install GitHub CLI

1. Go to https://cli.github.com
2. Click "Download for Windows"
3. Run the .msi installer
4. Use default options
5. Finish installation

---

## Step 4: Restart VSCode or Cursor IDE (Required!)

1. If VSCode or Cursor is open, close it completely (File → Exit)
2. Reopen VSCode or Cursor
3. Go to File → Open Folder
4. Create or select a folder for your project (like Documents/my-project)

---

## Step 5: Install Claude Code Extension

1. In VSCode or Cursor, find the **Extensions icon** in left sidebar (looks like 4 squares/blocks)
2. Click it
3. Search for: `claude code`
4. Click **Install** on "Claude Code"
5. Wait for install to complete
6. Look for **orange Claude icon** in RIGHT sidebar
7. Click orange icon to open Claude Code panel

---

## Step 6: Authenticate Claude Code

1. In Claude Code panel, click **"Sign in with Claude subscription"**
2. Browser opens - log in with your Claude Pro account
3. Approve the connection
4. Return to VSCode or Cursor

**Verify:** Claude Code panel no longer shows sign-in prompt

**If you see "only available for premium seats":** You need Claude Pro ($20/month individual) or ask your team admin to upgrade your seat from "Basic" to "Standard"

---

## Step 7: Authenticate GitHub CLI

1. In Cursor, go to Terminal → New Terminal (top menu)
2. A terminal panel opens at bottom
3. Type this command and press Enter:
   ```
   gh auth login
   ```
4. Use arrow keys to select **GitHub.com**, press Enter
5. Select **HTTPS**, press Enter
6. Select **Login with a web browser**, press Enter
7. Copy the one-time code shown
8. Press Enter - browser opens
9. Paste the code in browser
10. Click Authorize
11. Check your email for verification code if asked
12. Return to Cursor

**Verify:** Terminal shows "Logged in as [your-username]"

---

## Step 8: Clone Your Repository

1. Click the **orange Claude icon** to open Claude Code
2. Send this message (replace URL with your actual repository):
   ```
   Clone the repository https://github.com/YOUR-ORG/YOUR-REPO to this folder
   ```
3. Claude will ask to run a command - click **Yes**
4. Wait for cloning (1-5 minutes)

**Verify:** Left sidebar now shows folders and files from your repository

---

## Step 9: Test It Works

Send these messages to Claude Code:

1. "What files are in this repository?"
2. "Read the README and summarize it"
3. "What is this project about?"

**If Claude answers based on actual file contents, you're done!**

---

# Mac Setup

Mac requires a few extra steps because developer tools aren't pre-installed.

## Step 1: Install VSCode or Cursor IDE

1. Go to https://www.cursor.com or https://code.visualstudio.com/download
2. Download the Mac version (.dmg file)
3. Open the .dmg file from Downloads
4. **Drag** the Cursor or VSCode icon into the Applications folder
5. Open Finder → Applications → find Cursor or VSCode
6. **Right-click** Cursor or VSCode → **Open** (not double-click - this bypasses security warning)
7. Create a Cursor account (free) when prompted (if using Cursor)

**Verify:** Cursor or VSCode opens with welcome screen

---

## Step 2: Install Homebrew (Mac Package Manager)

Homebrew lets you install developer tools easily.

1. In Cursor, go to Terminal → New Terminal
2. Copy and paste this entire command:
   ```
   /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
   ```
3. Press Enter

⚠️ **PASSWORD INCOMING**: The next prompt asks for your Mac login password.
**YOUR TYPING WILL NOT SHOW ON SCREEN.** No dots, no asterisks, nothing.
This is normal. Type your password and press Enter.

4. When it says "Password:", type your Mac login password and press Enter
5. Wait for installation (5-15 minutes)
6. **IMPORTANT**: Follow any "Next steps" instructions shown at the end (usually adding Homebrew to your PATH)

---

## Step 3: Restart Terminal (Required!)

1. In the terminal, type `exit` and press Enter
2. Close the terminal panel
3. Open new terminal: Terminal → New Terminal

---

## Step 4: Install GitHub CLI

1. In the NEW terminal, type:
   ```
   brew install gh
   ```
2. Press Enter
3. Wait for installation (2-5 minutes)

**If you see "brew: command not found":** You need to restart the terminal again (Step 3)

---

## Step 5: Install Claude Code Extension

1. Find the **Extensions icon** in left sidebar (looks like 4 squares)
2. Click it
3. Search for: `claude code`
4. Click **Install** on "Claude Code"
5. Look for **orange Claude icon** in RIGHT sidebar
6. Click it to open Claude Code panel

---

## Step 6: Authenticate Claude Code

1. In Claude Code panel, click **"Sign in with Claude subscription"**
2. Browser opens - log in with your Claude Pro account
3. Approve the connection
4. Return to Cursor

**Verify:** Claude Code panel ready to use

---

## Step 7: Authenticate GitHub CLI

1. Open terminal if not open: Terminal → New Terminal
2. Type and press Enter:
   ```
   gh auth login
   ```
3. Select **GitHub.com** → Enter
4. Select **HTTPS** → Enter
5. Select **Login with a web browser** → Enter
6. Copy the one-time code shown
7. Press Enter - browser opens
8. Paste code in browser
9. Click Authorize
10. Enter email verification code if asked
11. Return to Cursor

**Verify:** Terminal shows "Logged in as [your-username]"

---

## Step 8: Create Project Folder and Clone

1. In Cursor: File → Open Folder
2. Navigate to Documents (or wherever you want)
3. Click "New Folder" - name it something like `projects`
4. Open that folder
5. Click **orange Claude icon** to open Claude Code
6. Send message (replace with your repo URL):
   ```
   Clone the repository https://github.com/YOUR-ORG/YOUR-REPO to this folder
   ```
7. Click **Yes** when Claude asks to run command
8. Wait for cloning

**Verify:** File tree in left sidebar shows your repository contents

---

## Step 9: Test It Works

Send these messages to Claude Code:

1. "What files are in this repository?"
2. "Read the README and summarize it"
3. "What is this project about?"

**If Claude answers based on actual file contents, you're done!**

---

# Troubleshooting

## Diagnostic Commands

**When something goes wrong, run these and share the output with your AI assistant:**

```bash
git --version
gh --version
gh auth status
```

**Interpreting results:**

| Output | Meaning | Fix |
|--------|---------|-----|
| `command not found` | Tool not installed OR terminal needs restart | Restart terminal, then install if still missing |
| Version number shows | Tool is installed correctly | Move to next step |
| `gh auth status` → "not logged in" | GitHub CLI not authenticated | Run `gh auth login` |
| `gh auth status` → "Logged in to github.com as X" | GitHub auth working | Auth is fine, issue is elsewhere |

---

## Common Issues

### "brew: command not found"
Close terminal, open new terminal, try again. If still failing, Homebrew didn't install correctly - re-run the install command.

### "gh: command not found"
Close terminal, open new terminal. If still failing on Mac, make sure Homebrew installed successfully first.

### Claude Code won't authenticate
- Verify you have Claude Pro ($20/month) or Standard/Premium team seat
- **Free tier does NOT work** - this is the most common issue
- Log out of claude.ai in browser, log back in, try again
- Close and reopen the Claude Code panel in Cursor

### "Repository not found" when cloning
- Check URL is correct (copy from GitHub website)
- Verify you have access to the repo (can you see it on github.com?)
- Run `gh auth status` - make sure it shows you're logged in

### Authentication asks for password repeatedly
The `gh auth login` flow should handle this. If Git keeps asking for username/password, run `gh auth login` again and make sure you select HTTPS and web browser authentication.

### Terminal commands don't work after install
Always close and reopen terminal after installing new tools. On Windows, you may need to restart Cursor entirely.

---

# Quick Reference

| Task | Command |
|------|---------|
| Check Git installed | `git --version` |
| Check GitHub CLI installed | `gh --version` |
| Check GitHub auth status | `gh auth status` |
| Clone a repo | `git clone [URL]` |
| Pull latest changes | `git pull` |

---

# Quick Setup (Experienced Users)

Already comfortable with terminal? Here's the condensed version:

### Mac
```bash
# Install tools (skip if you have them)
brew install gh

# Authenticate GitHub
gh auth login
# → Select: GitHub.com → HTTPS → Login with web browser

# Then: Install Claude Code extension in VSCode or Cursor, sign in with Claude Pro
```

### Windows
```
1. Download & install Git: https://git-scm.com/download/win
2. Download & install GitHub CLI: https://cli.github.com
3. Restart VSCode or Cursor IDE
4. In terminal: gh auth login
   → Select: GitHub.com → HTTPS → Login with web browser
5. Install Claude Code extension, sign in with Claude Pro
```

---

# What You Can Do Now

You can ask Claude Code anything about your repository:

- "What files are in the /docs folder?"
- "Summarize our brand voice guidelines"
- "Write a social post about X using our messaging"
- "Find all mentions of [competitor]"
- "What's our pricing strategy?"

Claude Code sees all your files and can read, search, and help you work with them.

---

**Setup complete! Start using Claude Code like ChatGPT, but with full access to your codebase.**
