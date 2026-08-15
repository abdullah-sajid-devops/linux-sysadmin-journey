# Day 45 of Cisco Linux Essentials Course

Covered Shell Scripting basics today — and passed Chapter 11 and Chapter 12 exams both with **80%**.

## Why Shell Scripting Matters

Every sysadmin/DevOps engineer needs this skill. Tasks that would take hours to complete manually, one command at a time, can be done in minutes with a script.

**In simple terms:** Shell scripting is taking your repetitive daily commands, saving them into a text file, and having them execute line by line automatically.

## Two Ways to Execute a Script

**Method 1:**
```bash
sh test.sh
bash test.sh
```
Doesn't require the script file to have execute permission.

**Method 2:**
```bash
./test.sh
```
Running it directly like this requires the file to have execute permission set first (`chmod +x test.sh`).

## The Shebang (`#!`)

The very first line of a script defines the interpreter:
```bash
#!/bin/bash
```
This tells the operating system exactly which shell should process the commands inside the file.

## Scripting's Three Fundamental Pillars

For real automation, three building blocks come together:

- **Variables** — for storing temporary information/data
- **Conditionals (if/else)** — for logical decision-making
- **Loops** — for repeating a task's execution

## What's Next

6 chapters left in the course — wrapping it up to get the certification, then moving into KodeKloud for deeper hands-on, practical labs.

#Linux #DevOps #CiscoNetworkingAcademy #LearningInPublic #ShellScripting
