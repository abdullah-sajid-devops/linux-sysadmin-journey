# Day 8: Linux File Permissions & Ownership Commands 🔐

## Overview
Practiced 4 essential File Permission & Ownership Commands
hands-on on a live Ubuntu Server as part of my
100 Days DevOps & Cloud Engineering Challenge.

---

## Commands Mastered Today

| # | Command | Description | Hands-on Example |
|---|---------|-------------|------------------|
| 1 | `chmod` | Change file access permissions | `chmod 745 newfile.txt` |
| 2 | `chattr` | Change special file attributes | `chattr +i file.txt` |
| 3 | `chown` | Change file owner and group | `chown vboxuser sample.txt` |
| 4 | `chgrp` | Change group ownership of file | `chgrp geeksforgeeks abc.txt` |

---

## Deep Dive: Understanding chmod Numbers

| Number | Permission | Meaning |
|--------|-----------|---------|
| 0 | --- | No permission |
| 1 | --x | Execute only |
| 2 | -w- | Write only |
| 3 | -wx | Write + Execute |
| 4 | r-- | Read only |
| 5 | r-x | Read + Execute |
| 6 | rw- | Read + Write |
| 7 | rwx | Full permission |

### Example: chmod 745
- **7** → Owner: Read + Write + Execute (full access)
- **4** → Group: Read only
- **5** → Others: Read + Execute

### Common chmod Values
| Command | Meaning |
|---------|---------|
| `chmod 777` | Everyone gets full access — dangerous! |
| `chmod 755` | Owner full, Group & Others read+execute |
| `chmod 644` | Owner read+write, Group & Others read only |
| `chmod 400` | Owner read only — used for SSH keys |

---

## Key Learnings

- **`chmod`** — Most used permission command in Linux.
  Works in both numeric (755) and symbolic (+x) modes.
- **`chattr +i`** — Makes file completely immutable.
  Even root cannot delete or modify it. Perfect for
  protecting critical system files.
- **`chown`** — Essential in multi-user server environments.
  Used to assign correct ownership after file transfers.
- **`chgrp`** — Useful for team-based file sharing.
  Assigns files to specific groups for shared access.
- **Security Rule:** Never use `chmod 777` on production
  servers — it gives everyone full access and is a
  major security risk!

---

## Environment
- **OS:** Ubuntu Server (AWS EC2)
- **Source:** GeeksForGeeks Linux Track
- **Status:** ✅ All commands practiced on live terminal

---

*Part of my 100 Days DevOps & Cloud Engineering Challenge*
*Follow my journey: [LinkedIn](https://www.linkedin.com/in/abdullah-sajid-azure)*
