# Day 32: Man Page Sections, whatis, apropos, whereis & locate 📚

Day 32 of my Linux learning journey. Today's focus was on how Linux 
handles command documentation, file paths, and system-wide file 
searching.

---

## 📖 1. Navigating Man Page Sections

Commands and files can share the same name — for example, `passwd` is 
both a command and a file at `/etc/passwd`. Section numbers let you 
access the specific documentation you actually need:

- `man 1 passwd` → user command
- `man 5 passwd` → file format / configuration
- `man 8 <command>` → system administration commands

---

## 🔎 2. Quick Documentation Search

- `whatis` (or `man -f`) → displays available manual sections for a command
- `apropos` (or `man -k`) → searches manuals by keyword when you don't 
  remember the exact command name

---

## 📂 3. Finding Executables & Documentation Paths

`whereis <command>` → instantly locates the binary executable path and 
the compressed (`.gz`) man page files.

---

## ⚡ 4. Fast File Searching with `locate`

- `locate` searches a pre-built system database, not the live filesystem 
  — that's why it's so fast
- `updatedb` (run with root privileges) indexes newly created files 
  into that database
- Useful flags: `-c` (count), `-b` (basename only), `\` for exact matches

---

## 📝 Quiz Result
Tested myself with a quick 10-question quiz right after — scored **90%**.

---

## 🔜 Next Step
Continuing with NDG Linux Essentials.
