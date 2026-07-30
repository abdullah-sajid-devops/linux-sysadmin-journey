# Day 35 of my Linux learning journey

Understanding how to efficiently navigate and manage files in the CLI is essential. Here's a breakdown of key file system concepts and `ls` command shortcuts.

## Absolute vs relative paths

- **Absolute path:** the complete address from the root directory (`/`). Always takes you to the exact location, e.g. `cd /home/sysadmin/Documents`
- **Relative path:** directions based on your current working directory
  - `cd School/Art` — moves into a subfolder
  - `cd ..` — moves one level up
  - `cd ../..` — moves two levels up
  - `.` — refers to the current directory itself

## Mastering the ls command

- **Hidden files** (`ls -a`) — reveals hidden files/folders starting with a dot (.bashrc, .profile)
- **Detailed view** (`ls -l`) — shows file type, permissions, owners, size, timestamp
- **Readable sizes** (`ls -lh`) — displays sizes in KB/MB/GB instead of raw bytes
- **Directory info** (`ls -ld`) — lists details of the directory itself, not its contents
- **Recursive search** (`ls -R`) — lists all files including sub-directories, level by level

## Sorting output like a pro

- `ls -lS` — sorts files by size, largest first
- `ls -lt` — sorts files by modification time, newest first
- `ls -lrt` — reverses the sort, useful for oldest/newest modified files

Understanding these CLI building blocks makes troubleshooting, log analysis, and navigating servers so much faster.

#Linux #CloudComputing #DevOps #SystemAdministration #OpenSource #LearningInPublic #Bash
