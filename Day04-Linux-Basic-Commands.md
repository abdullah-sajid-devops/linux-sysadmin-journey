# Day 4: 100 Days of DevOps - Linux Basic Commands Mastery 🐧

Today I covered the fundamental core Linux commands on my Ubuntu server via GeeksforGeeks. Practiced system navigation, file operations, identity checking, text manipulations, and file statistics.

## 🛠️ Commands Practiced & Mastered:

| Command | Category | Description | Hands-on Example |
| :--- | :--- | :--- | :--- |
| `pwd` | Navigation | Print Working Directory | `pwd` |
| `ls -la` | Navigation | Long list all files including hidden ones | `ls -la` |
| `cd` | Navigation | Change directory / move between folders | `cd gfg_files` |
| `mkdir -p` | Navigation | Create nested folder paths seamlessly | `mkdir -p project/src` |
| `touch` | File Ops | Create empty file or update timestamp | `touch server.log` |
| `cp` | File Ops | Copy files/directories | `cp config.json backup.json` |
| `mv` | File Ops | Move or rename files/directories | `mv old_name.txt new_name.txt` |
| `rm -rf` | File Ops | Forcefully and recursively remove directories | `rm -rf test_folder` |
| `echo` | Text Ops | Print text or append data to files using `>` | `echo "Active" > status.txt` |
| `cat` | Text Ops | Display whole file content on terminal | `cat status.txt` |
| `grep` | Search Ops | Global Regular Expression Print (Find words) | `grep "Active" status.txt` |
| `clear` | Utility | Clean the terminal window screen | `clear` |
| `whoami` | System Info | Check current logged in user account | `whoami` |
| `uname -a` | System Info | Check OS kernel and architecture details | `uname -a` |
| `df -h` | System Info | Display disk space usage in human-readable GBs | `df -h` |
| `ps aux` | System Info | Monitor all active running system processes | `ps aux` |
| `man` | Utility | Open internal reference manual for commands | `man mkdir` |
| `wget` | Network | Download files directly from the web/internet | `wget https://google.com` |
| `whereis` | Search Ops | Locate binary, source, and manual page for command| `whereis ls` |
| `ln -s` | File Ops | Create symbolic soft links (shortcuts) | `ln -s main.py link.py` |
| `sort` | Text Ops | Sort lines of text files alphabetically | `sort names.txt` |
| `locate` | Search Ops | Find files by name using system database | `locate bash` |
| `wc -l` | Text Ops | Count the exact total number of lines in a file | `wc -l logs.txt` |

## 🚀 Key Takeaway:
Command-line familiarity is non-negotiable for Cloud Engineers. Mastering flags like `df -h`, `ls -la`, and `wc -l` enables fast backend diagnosis on heavy infrastructure servers.
