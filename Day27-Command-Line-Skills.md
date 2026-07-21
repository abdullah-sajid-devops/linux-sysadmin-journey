# Day 27 of Cisco Linux Essentials Course

Today I started Chapter 5 — Command Line Skills.

## Why the Command Line Matters
Linux celebrates the CLI for its power, speed, and ability to accomplish tasks with a single instruction. Once you understand command structure, you become highly productive — and this skill transfers across ANY Linux distribution.

## The Shell
The shell is the command line interpreter that translates typed commands into actions performed by the OS. The most common shell is **Bash**, which offers:
- **Scripting** — writing a file of commands to execute together
- **Aliases** — short nicknames for longer commands
- **Variables** — storing information for the shell to use

## Understanding the Prompt
Example: `sysadmin@localhost:~$`
- `sysadmin` → username
- `localhost` → system name
- `~` → current directory (home directory shorthand)

## Commands, Options & Arguments
Basic format: `command [options] [arguments]`

- **Arguments** — what the command acts on, e.g. `ls /etc/ppp`
- **Options** — modify command behavior, e.g.:
  - `ls -l` → long listing (permissions, size, etc.)
  - `ls -r` → reverse order
  - `ls -lr` or `ls -rl` → combined options, same result
  - `ls -lh` → human-readable file sizes (e.g., 11K instead of 10376 bytes)
  - `ls -l --human-readable` → full-word equivalent option

**Note:** Linux is case-sensitive — commands, options, and file names must be entered exactly as shown.

#Linux #DevOps #CiscoNetworkingAcademy #LearningInPublic #CommandLine
