# Day 7: Linux Directory Operation Commands 🐧

## Overview
Practiced 12 essential Directory Operation Commands hands-on
on a live Ubuntu Server as part of my
100 Days DevOps & Cloud Engineering Challenge.

---

## Commands Mastered Today

| # | Command | Description | Hands-on Example |
|---|---------|-------------|------------------|
| 1 | `cd` | Change current directory | `cd Documents` |
| 2 | `dir` | Display files and folders in current directory | `dir` |
| 3 | `dirname` | Extract directory path from full file path | `dirname /Desktop/root/bash.sh` |
| 4 | `dirs` | Show directory navigation history (stack) | `dirs` |
| 5 | `du` | Show disk usage of directories and files | `du -h` |
| 6 | `find` | Search files/directories recursively | `find ./gfg -name "sample.txt"` |
| 7 | `lsblk` | Display storage devices and mount points | `lsblk` |
| 8 | `mkdir` | Create new directories | `mkdir my_folder` |
| 9 | `mount` | Attach filesystem to a directory | `mount /dev/sda1 /mnt` |
| 10 | `pwd` | Display current working directory path | `pwd` |
| 11 | `rmdir` | Delete empty directories only | `rmdir empty_folder` |
| 12 | `tree` | Display directory structure visually | `tree -a ./GFG` |

---

## Key Learnings

- **`find`** — Most powerful search command in Linux.
  Searches recursively by name, type, size, or permissions.
  Every DevOps Engineer uses this for log hunting on
  production servers.
- **`tree`** — Visual folder hierarchy — instantly shows
  entire directory structure at a glance.
- **`du -h`** — Human readable disk usage. Essential for
  identifying folders consuming excess storage.
- **`lsblk`** — Shows all block devices and partitions.
  Critical for storage and disk management.
- **`mount`** — Attaches storage devices to filesystem.
  Important system administration command.
- **`rmdir` vs `rm -r`** — `rmdir` only removes empty
  directories. `rm -r` removes directories with content
  — use carefully!
- **`dirs`** — Tracks directory navigation history.
  Works with `pushd` and `popd` for advanced navigation.

---

## Environment
- **OS:** Ubuntu Server (AWS EC2)
- **Source:** GeeksForGeeks Linux Track
- **Status:** ✅ All commands practiced on live terminal

---

*Part of my 100 Days DevOps & Cloud Engineering Challenge*
*Follow my journey: [LinkedIn](https://www.linkedin.com/in/abdullah-sajid-devops)*
