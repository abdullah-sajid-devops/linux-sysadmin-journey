# Day 13: Linux Job Scheduling & Automation Commands

## Overview
Job scheduling and automation are critical components of Linux system administration. They allow administrators to automate repetitive tasks, execute shell scripts, and run maintenance activities at specific times or system states without manual intervention. Today, I explored the key utilities used for scheduling one-time and recurring jobs in Linux.

---

## 1. One-Time Job Scheduling (`at` Suite)

The `at` command suite is designed to execute a specific task or command exactly once at a specified future time. 

### A. `atd` (At Daemon)
* **Purpose:** The background daemon responsible for checking and executing jobs queued by the `at` command.
* **Service Management:**
  ```bash
  sudo systemctl status atd   # Check if the at daemon is running
  sudo systemctl start atd    # Start the daemon
B. at (Schedule a Job)
Purpose: Queues a command or script to run once at a specific time.

Syntax & Examples:

Bash
# Schedule a task at a specific time (e.g., 11:00 PM)
at 23:00

# Schedule a task to run after a relative offset
at now + 10 minutes
at tomorrow 4pm
Note: After entering the command, type your desired execution commands and press Ctrl+D to save and exit.

C. atq (List Pending Jobs)
Purpose: Displays a list of currently scheduled, pending jobs for the user.

Command:

Bash
atq
D. atrm (Remove Scheduled Jobs)
Purpose: Deletes a specific job from the execution queue using its unique Job ID.

Command:

Bash
# Remove job number 3 from the queue
atrm 3
2. Idle-Time Job Scheduling (batch)
batch (Run When System is Idle)
Purpose: Similar to at, but it doesn't execute at a strict time. Instead, it queues tasks to execute only when the system's CPU load average drops below a predefined threshold (typically 1.5).

Usage:

Bash
batch
# Enter commands to execute when the system is free, then press Ctrl+D
3. Recurring Job Scheduling (cron Suite)
For periodic and recurring automated tasks (e.g., daily backups, weekly log rotations), Linux uses the cron system daemon.

A. cron (Cron Daemon)
Purpose: A system-wide daemon that runs continuously in the background, waking up every minute to check the crontab files for tasks scheduled to run.

B. crontab (Manage Cron Tables)
Purpose: The configuration file and tool used by individual users to define scheduled cron jobs.

Key Commands:

Bash
crontab -e   # Edit the current user's crontab file
crontab -l   # List all scheduled cron jobs for the current user
crontab -r   # Remove/Delete all cron jobs for the current user
Crontab Syntax Structure
A crontab entry consists of 5 time fields followed by the absolute path of the command or script to execute:

Plaintext
 .---------------- minute (0 - 59)
 |  .------------- hour (0 - 23)
 |  |  .---------- day of month (1 - 31)
 |  |  |  .------- month (1 - 12)
 |  |  |  |  .---- day of week (0 - 6) (Sunday=0 or 7)
 |  |  |  |  |
 *  *  *  *  *  /path/to/command_or_script
Common Configuration Examples:
Run a backup script every day at midnight:

Plaintext
0 0 * * * /home/user/scripts/backup.sh
Run a clean-up script every Sunday at 4:30 AM:

Plaintext
30 4 * * 0 /usr/local/bin/cleanup.sh
Run a health-check script every 15 minutes:

Plaintext
*/15 * * * * /home/user/scripts/health_check.sh
Practical Implementation & Verification
Verified the status of atd and cron services using systemctl.

Created a dummy one-time alert using at now + 5 minutes and verified its execution.

Created and listed standard cron expressions using crontab -e and crontab -l to log automated uptime statuses.
