# Day 32 of Cisco Linux Essentials Course

Today I deep-dived into how Linux handles command documentation, file paths, and system-wide file searching.

## Navigating Man Page Sections
Commands and files can share the same name (e.g., `passwd` command vs `/etc/passwd` file). Section numbers let us access specific documentation:
- `man 1 passwd` → User command
- `man 5 passwd` → File format configuration
- `man 8 <command>` → System administration commands

## Quick Documentation Search
- `whatis` (or `man -f`) → Displays available manual sections for a command
- `apropos` (or `man -k`) → Searches manuals using keywords when you forget the exact command name

## Finding Executables & Documentation Paths
`whereis <command>` → Instantly locates the binary executable path and compressed (`.gz`) man page files.

## Fast File Searching with `locate`
- `locate` searches a pre-built system database for ultra-fast results
- `updatedb` (with root privileges) indexes newly created files
- Filter results using `-c` (count), `-b` (basename only), or `\` for exact matches

Tested with a quick 10-question quiz — scored 90%.

#Linux #DevOps #CiscoNetworkingAcademy #LearningInPublic #SysAdmin
