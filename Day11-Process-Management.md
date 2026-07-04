# Day 11: Linux Process Management Commands ⚙️

## Overview
Practiced 18 essential Process Management Commands hands-on
on a live Ubuntu Server as part of my
100 Days DevOps & Cloud Engineering Challenge.

---

## Commands Mastered Today

| # | Command | Description | Hands-on Example |
|---|---------|-------------|------------------|
| 1 | `accton` | Enable or disable process accounting | `accton /var/log/pacct` |
| 2 | `bg` | Resume suspended job in background | `bg %1` |
| 3 | `chrt` | Change real-time scheduling of a process | `chrt -f 10 ./script.sh` |
| 4 | `fg` | Bring background job to foreground | `fg %1` |
| 5 | `kill` | Terminate a process by PID | `kill -9 1234` |
| 6 | `mpstat` | Display CPU usage per processor | `mpstat -P ALL` |
| 7 | `pidof` | Find PID of a running program | `pidof nginx` |
| 8 | `pmap` | Display memory map of a process | `pmap 1234` |
| 9 | `ps` | Show current running processes | `ps aux` |
| 10 | `top` | Real-time process monitoring | `top` |
| 11 | `htop` | Interactive process viewer (enhanced top) | `htop` |
| 12 | `strace` | Trace system calls of a process | `strace -p 1234` |
| 13 | `time` | Measure execution time of a command | `time ./script.sh` |
| 14 | `watch` | Execute command repeatedly at intervals | `watch -n 2 df -h` |
| 15 | `vmstat` | Report virtual memory statistics | `vmstat 1 5` |
| 16 | `uptime` | Show how long system has been running | `uptime` |
| 17 | `w` | Show who is logged in and what they are doing | `w` |
| 18 | `mpstat` | Monitor CPU performance statistics | `mpstat 1` |

---

## Key Learnings

- **`top` & `htop`** — Real time process monitoring.
  Every DevOps Engineer has this open on production
  servers 24/7. `htop` is more interactive than `top`.
- **`kill -9`** — Force kill any process instantly.
  Use with caution — always try `kill -15` first
  for graceful termination.
- **`ps aux`** — Most used process command.
  Shows all running processes with CPU and memory usage.
- **`strace`** — Powerful debugging tool.
  Traces every system call a process makes.
  Essential for debugging complex issues.
- **`watch -n 2`** — Runs any command every 2 seconds.
  Perfect for monitoring real-time changes.
- **`uptime`** — Shows server running time.
  High uptime = healthy infrastructure in DevOps!
- **`bg` & `fg`** — Background/foreground job control.
  Essential for managing multiple tasks in terminal.
- **`vmstat`** — Shows memory, CPU, and I/O stats.
  Critical for performance troubleshooting.

---

## Process Management Workflow

Monitor → Identify → Control → Verify
ps/top    pidof      kill/bg    watch/top

---

## Important Signals for kill Command

| Signal | Number | Meaning |
|--------|--------|---------|
| SIGTERM | 15 | Graceful termination (try first) |
| SIGKILL | 9 | Force kill (last resort) |
| SIGHUP | 1 | Reload configuration |
| SIGSTOP | 19 | Pause/suspend process |

---

## Environment
- **OS:** Ubuntu Server (AWS EC2)
- **Source:** GeeksForGeeks Linux Track
- **Status:** ✅ All commands practiced on live terminal

---

*Part of my 100 Days DevOps & Cloud Engineering Challenge*
*Follow my journey: [LinkedIn](https://www.linkedin.com/in/abdullah-sajid-azure)*
