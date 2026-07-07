# Day 14: Linux Disk & File System Commands 💾

## Overview
Practiced 9 essential Disk & File System Commands hands-on
on a live Ubuntu Server as part of my
100 Days DevOps & Cloud Engineering Challenge.

---

## Commands Mastered Today

| # | Command | Description | Hands-on Example |
|---|---------|-------------|------------------|
| 1 | `cfdisk` | Interactive disk partition manager | `cfdisk /dev/sda` |
| 2 | `df` | Display disk space usage | `df -h` |
| 3 | `dosfsck` | Check and repair FAT file systems | `dosfsck /dev/sdb1` |
| 4 | `dump` | Backup entire filesystem | `dump -0uf /backup/full.dump /dev/sda1` |
| 5 | `dumpe2fs` | Display ext2/ext3/ext4 filesystem info | `dumpe2fs /dev/sda1` |
| 6 | `fdisk` | Partition table manipulator | `fdisk -l` |
| 7 | `mount` | Attach filesystem to directory | `mount /dev/sdb1 /mnt` |
| 8 | `restore` | Restore files from dump backup | `restore -rf /backup/full.dump` |
| 9 | `sync` | Flush cached data to disk | `sync` |

---

## Key Learnings

- **`sync`** — Most critical command in this module.
  Forces all cached data to be written to disk.
  Always run before shutting down a server to
  prevent data loss in production! ⚠️
- **`fdisk` vs `cfdisk`** — Both manage partitions.
  `fdisk` is command-line based, `cfdisk` is
  interactive with a visual interface. Easier for
  beginners!
- **`df -h`** — Human readable disk usage.
  `-h` flag shows GB/MB instead of raw bytes.
  Most used disk monitoring command in DevOps.
- **`dump` + `restore`** — Classic Linux backup pair.
  `dump` creates the backup, `restore` recovers it.
  Used for full filesystem backups.
- **`dumpe2fs`** — Shows detailed filesystem info
  including block size, mount count, and last
  check time. Essential for filesystem debugging.
- **`dosfsck`** — FAT filesystem checker.
  Used when dealing with USB drives or Windows
  partitions on Linux servers.
- **`mount`** — Attaches any storage device to the
  filesystem. Without mounting — device is not
  accessible in Linux!

---

## Disk Management Workflow
Check Disk → Partition → Format → Mount → Use → Backup
df          fdisk       mkfs      mount         dump

---

## fdisk vs cfdisk Comparison

| Feature | `fdisk` | `cfdisk` |
|---------|---------|---------|
| Interface | Command-line | Interactive/Visual |
| Difficulty | Advanced | Beginner friendly |
| Best for | Scripting | Manual partitioning |

---

## 2 Week Milestone ✅

| Days | Topics Covered |
|------|---------------|
| Week 1 (Day 1-7) | IAM, Storage, FHS, CLI, File Ops, Directory Ops |
| Week 2 (Day 8-14) | Permissions, Users, Groups, Processes, Terminal, Jobs, Disk |

**14 days. 14 topics. Zero skipped. Streak alive! 🔥**

---

## Environment
- **OS:** Ubuntu Server (AWS EC2)
- **Source:** GeeksForGeeks Linux Track
- **Status:** ✅ All commands practiced on live terminal

---

*Part of my 100 Days DevOps & Cloud Engineering Challenge*
*Follow my journey: [LinkedIn](https://www.linkedin.com/in/abdullah-sajid-devops)*
