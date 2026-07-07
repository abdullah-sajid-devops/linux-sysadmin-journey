# Day 13: Linux Job Scheduling Commands ⏰

## Overview
Practiced 6 essential Job Scheduling Commands hands-on
on a live Ubuntu Server as part of my
100 Days DevOps & Cloud Engineering Challenge.

---

## Commands Mastered Today

| # | Command | Description | Hands-on Example |
|---|---------|-------------|------------------|
| 1 | `atd` | Daemon that runs scheduled at jobs | `systemctl start atd` |
| 2 | `atq` | List all pending at jobs | `atq` |
| 3 | `atrm` | Remove a scheduled at job | `atrm 2` |
| 4 | `batch` | Run jobs when system load is low | `batch` |
| 5 | `cron` | Daemon for recurring task scheduling | `systemctl status cron` |
| 6 | `crontab` | Manage personal cron job schedules | `crontab -e` |

---

## Deep Dive: Crontab Syntax









command_to_execute
│ │ │ │ │
│ │ │ │ └── Day of week (0-7, 0=Sunday)
│ │ │ └──── Month (1-12)
│ │ └────── Day of month (1-31)
│ └──────── Hour (0-23)
└────────── Minute (0-59)










### Common Crontab Examples

| Schedule | Crontab Expression |
|----------|--------------------|
| Every minute | `* * * * *` |
| Every hour | `0 * * * *` |
| Every day at midnight | `0 0 * * *` |
| Every Sunday at 2 AM | `0 2 * * 0` |
| Every 1st of month | `0 0 1 * *` |
| Every 5 minutes | `*/5 * * * *` |

---

## Key Learnings

- **`crontab`** — Most important job scheduling tool
  in Linux. Used everywhere in DevOps for:
  - Automated backups
  - Log cleanup
  - Health checks
  - Deployment scripts
- **`crontab -e`** — Edit your cron jobs
- **`crontab -l`** — List all your cron jobs
- **`crontab -r`** — Remove all cron jobs (careful!)
- **`atd`** — For one-time scheduled jobs.
  Perfect for running a script at a specific time.
- **`batch`** — Smart scheduling — runs only when
  system CPU load is below 0.8. Great for
  resource-intensive tasks.
- **`atq`** — Always check pending jobs before
  adding new ones to avoid conflicts.
- **`atrm`** — Remove jobs by job number shown in `atq`.

---

## Real World DevOps Use Cases

| Task | Crontab Schedule |
|------|-----------------|
| Daily backup at 2 AM | `0 2 * * *` |
| Log cleanup every Sunday | `0 0 * * 0` |
| Health check every 5 min | `*/5 * * * *` |
| Monthly report on 1st | `0 9 1 * *` |
| Restart service every hour | `0 * * * *` |

---

## at vs cron — When to Use What

| Feature | `at` | `cron` |
|---------|------|--------|
| Job type | One-time | Recurring |
| Use case | Single task | Regular automation |
| Example | Run backup now | Run backup daily |

---

## Environment
- **OS:** Ubuntu Server (AWS EC2)
- **Source:** GeeksForGeeks Linux Track
- **Status:** ✅ All commands practiced on live terminal

---

*Part of my 100 Days DevOps & Cloud Engineering Challenge*
*Follow my journey: [LinkedIn](https://www.linkedin.com/in/abdullah-sajid-azure)*
