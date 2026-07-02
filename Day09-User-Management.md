# Day 9: Linux User Management Commands 👥

## Overview
Practiced 15 essential User Management Commands hands-on
on a live Ubuntu Server as part of my
100 Days DevOps & Cloud Engineering Challenge.

---

## Commands Mastered Today

| # | Command | Description | Hands-on Example |
|---|---------|-------------|------------------|
| 1 | `chage` | Change user password expiry policy | `chage -l username` |
| 2 | `chfn` | Change user full name and info | `chfn username` |
| 3 | `chsh` | Change user default login shell | `chsh -s /bin/bash username` |
| 4 | `chpasswd` | Change passwords for multiple users | `echo "user:pass" \| chpasswd` |
| 5 | `finger` | Display user information | `finger username` |
| 6 | `id` | Display user ID and group ID | `id username` |
| 7 | `passwd` | Change user password | `passwd username` |
| 8 | `pinky` | Lightweight version of finger | `pinky username` |
| 9 | `username` | Display current username | `username` |
| 10 | `useradd` | Create a new user account | `useradd -m newuser` |
| 11 | `userdel` | Delete a user account | `userdel -r username` |
| 12 | `usermod` | Modify existing user account | `usermod -aG sudo username` |
| 13 | `users` | Show all currently logged in users | `users` |
| 14 | `who` | Show who is logged in with details | `who` |
| 15 | `whoami` | Display current logged in username | `whoami` |

---

## Key Learnings

- **`chage`** — Controls password expiry policies.
  In production environments, forcing regular password
  changes is a critical security practice.
- **`whoami` vs `who` vs `users`** — Three different
  commands, three different outputs:
  - `whoami` → just your username
  - `who` → who is logged in and when
  - `users` → all logged in users in one line
- **`useradd -m`** — `-m` flag creates home directory
  automatically. Always use it when adding new users.
- **`userdel -r`** — `-r` flag removes home directory
  along with user. Without `-r`, home directory remains.
- **`usermod -aG sudo`** — Adds user to sudo group.
  Critical command for granting admin privileges safely.
- **`chpasswd`** — Perfect for bulk password changes
  in scripts. Saves time in large server environments.
- **`id`** — Shows UID, GID and all groups a user
  belongs to. Essential for debugging permission issues.

---

## User Management Workflow

Create User → Set Password → Assign Groups → Set Expiry → Verify
useradd -m   passwd         usermod -aG    chage         id

---

## Environment
- **OS:** Ubuntu Server (AWS EC2)
- **Source:** GeeksForGeeks Linux Track
- **Status:** ✅ All commands practiced on live terminal

---

*Part of my 100 Days DevOps & Cloud Engineering Challenge*
*Follow my journey: [LinkedIn](https://www.linkedin.com/in/abdullah-sajid-azure)*
