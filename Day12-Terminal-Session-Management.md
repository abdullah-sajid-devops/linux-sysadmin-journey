# Day 12: Linux Terminal & Session Management Commands 🖥️

## Overview
Practiced 8 essential Terminal & Session Management Commands
hands-on on a live Ubuntu Server as part of my
100 Days DevOps & Cloud Engineering Challenge.

---

## Commands Mastered Today

| # | Command | Description | Hands-on Example |
|---|---------|-------------|------------------|
| 1 | `agetty` | Manages terminal login prompts | `agetty 9600 tty1` |
| 2 | `chvt` | Switch between virtual terminals | `chvt 2` |
| 3 | `reset` | Reset terminal to normal state | `reset` |
| 4 | `screen` | Run multiple terminal sessions | `screen -S mysession` |
| 5 | `showkey` | Display keyboard key codes | `showkey` |
| 6 | `stty` | Change terminal settings | `stty -a` |
| 7 | `tty` | Display current terminal name | `tty` |
| 8 | `xdg-open` | Open file/URL from terminal | `xdg-open file.pdf` |

---

## Key Learnings

- **`screen`** — Most powerful command in this module.
  Lets you run multiple terminal sessions inside one window.
  Even if SSH connection drops — processes keep running!
  Essential for long-running tasks on remote servers.
- **`reset`** — When terminal gets messed up with weird
  characters — one command fixes everything instantly!
- **`tty`** — Shows which terminal you are currently
  using. Useful when working with multiple sessions.
- **`stty`** — Controls terminal behavior like
  backspace, line endings, and special characters.
- **`chvt`** — Switch between virtual terminals
  without closing current session.
- **`agetty`** — Manages terminal login — runs in
  background on every Linux system automatically.
- **`xdg-open`** — Opens any file with its default
  application directly from terminal.
- **`showkey`** — Shows key codes when keys are pressed.
  Useful for keyboard configuration and scripting.

---

## screen Command — Deep Dive

```bash
# Start new named session
screen -S mysession

# List all sessions
screen -ls

# Detach from session (keep running)
Ctrl + A, then D

# Reattach to session
screen -r mysession

# Kill a session
screen -X -S mysession quit
```

**Why screen matters in DevOps:**
When connected to a remote server via SSH and running
a long task — if connection drops, task stops.
With `screen` — task keeps running in background!

---

## Environment
- **OS:** Ubuntu Server (AWS EC2)
- **Source:** GeeksForGeeks Linux Track
- **Status:** ✅ All commands practiced on live terminal

---

*Part of my 100 Days DevOps & Cloud Engineering Challenge*
*Follow my journey: [LinkedIn](https://www.linkedin.com/in/abdullah-sajid-azur)*
