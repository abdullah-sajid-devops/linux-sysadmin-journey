# Day 5: Linux File Operational Commands 🐧

## Overview
Practiced 20 essential File Operational Commands hands-on 
on a live Ubuntu Server as part of my 
100 Days DevOps & Cloud Engineering Challenge.

---

## Commands Mastered Today

| # | Command | Description | Hands-on Example |
|---|---------|-------------|------------------|
| 1 | `basename` | Extracts filename from full path | `basename /home/user/file.txt` |
| 2 | `cat` | Display/concatenate file content | `cat file.txt` |
| 3 | `cksum` | Verify file integrity via CRC checksum | `cksum file.txt` |
| 4 | `cmp` | Compare two files byte by byte | `cmp file1.txt file2.txt` |
| 5 | `compress` | Compress files into .Z format | `compress example.txt` |
| 6 | `cp` | Copy files or directories | `cp file1.txt file2.txt` |
| 7 | `cpio` | Create/extract archive for backups | `ls \| cpio -o > backup.cpio` |
| 8 | `csplit` | Split file by pattern or line number | `csplit file.txt /pattern/` |
| 9 | `cut` | Extract specific columns from file | `cut -d',' -f1 file.csv` |
| 10 | `diff` | Compare two files line by line | `diff a.txt b.txt` |
| 11 | `diff3` | Compare three files simultaneously | `diff3 a.txt b.txt c.txt` |
| 12 | `echo` | Print text or variables to terminal | `echo "Hello Linux"` |
| 13 | `expand` | Convert tabs into spaces | `expand file.txt` |
| 14 | `file` | Identify file type (not by extension) | `file script.sh` |
| 15 | `fold` | Wrap long lines to specified width | `fold -w60 file.txt` |
| 16 | `head` | Display first 10 lines of a file | `head sample.txt` |
| 17 | `less` | View file content page by page | `less file.txt` |
| 18 | `join` | Merge two files by common field | `join file1.txt file2.txt` |
| 19 | `ln` | Create hard or symbolic links | `ln -s file.txt link.txt` |
| 20 | `locate` | Fast file search using database | `locate file.txt` |

---

## Key Learnings

- **`diff` vs `cmp`** — diff shows line-by-line differences,
  cmp works byte by byte. Both have different DevOps use cases.
- **`head`** — shows first 10 lines by default.
  Extremely useful for checking log files quickly.
- **`ln -s`** — creates a symbolic link, works like 
  a shortcut in Windows.
- **`less`** — faster than `more` for large files because 
  it does not load entire file into memory.
- **`locate`** — much faster than `find` because 
  it uses a pre-built database.
- **`cksum`** — used to verify file integrity after 
  transfers, important in server environments.

---

## Environment
- **OS:** Ubuntu Server (AWS EC2)
- **Source:** GeeksForGeeks Linux Track
- **Status:** ✅ All commands practiced on live terminal

---

*Part of my 100 Days DevOps & Cloud Engineering Challenge*  
*Follow my journey: [LinkedIn](https://www.linkedin.com/in/abdullah-sajid-azure)*
