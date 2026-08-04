# Day 38 of Cisco Linux Essentials Course

Managing files and folders through the CLI is where Linux's real power shows. Two important things to keep in mind before diving into wildcards:

## Case Sensitivity

Linux is case-sensitive — capital and small letters are treated as completely different.

**Example:** `hello.txt`, `Hello.txt`, `HELLO.txt` are three separate files.

## UTF-8 & ASCII Standards

Linux uses the UTF-8 standard for characters, which is based on ASCII.

---

## Globbing (Wildcards)

Globs are special symbols that help the shell build filename matching patterns.

**Benefit:** Instead of touching one file at a time, you can match a pattern and run a command on hundreds of files at once.

### Asterisk (`*`) Character

**Rule:** `*` means zero or more characters.

```bash
echo /etc/t*        # Files in /etc starting with "t" (anything or nothing after)
echo /etc/*.d       # Files ending in ".d"
echo /etc/r*.conf   # Files starting with "r" and ending in ".conf"
```

### Question Mark (`?`) Character

**Rule:** `?` means exactly ONE character.

```bash
echo /etc/t???????              # Starts with "t", followed by exactly 7 more characters (8 total)
echo /etc/*.???                 # Files with exactly a 3-letter extension (e.g. .net, .gen)
echo /etc/*????????????????????? # Files with 20+ characters in the name
```

### Bracket `[ ]` Characters

**1. Specific Character Selection**

Characters inside brackets match any ONE of them.

```bash
echo /etc/[gu]*
```
Meaning: files in `/etc` starting with either `g` OR `u`.

**2. Character Ranges (using `-`)**

```bash
echo /etc/[a-d]*      # Files starting with a, b, c, or d
echo /etc/*[0-9]*     # Files containing at least one number (0-9) anywhere in the name
```

### Exclamation Point (`!`) Character — Negation

Placing `!` at the start of a bracket **excludes** the letters/range inside it.

```bash
/etc/[!DP]*        # Files NOT starting with D or P
echo /etc/[!a-t]*  # Files NOT starting with any letter from a to t
                    # (only u-z, capitals, or numbers will match)
```

**Pro-tip:** Some shells also accept `^` instead of `!` for negation (e.g. `[^0-9]`), but the Linux Essentials course focuses on `!`.

---

## The `ls` Command + Globbing "Twist"

`echo` handles globs in a very straightforward way. `ls` behaves differently.

**The problem:**
- If the argument is a **file** → `ls /etc/adduser.conf` just prints that file's details.
- If the argument is a **directory** → `ls /etc/apparmor` does NOT print the directory's own name — it lists everything **inside** it instead.

So when you run:
```bash
ls /etc/ap*
```
The shell expands this glob into three paths: `/etc/apparmor`, `/etc/apparmor.d`, and `/etc/apt` — all directories. Since they're directories, `ls` dumps the **contents of each one** onto the screen, making the output messy and confusing.

**The Solution: `-d` Flag**

```bash
ls -d /etc/ap*
```
This tells `ls`: "Don't show me what's inside the directory — just list the directory's own name."

---

## Copying Files (`cp` Command)

### Basic Syntax

```bash
cp source destination
```

### The "Silence Rule"

Linux CLI principle: if the copy succeeds, `cp` shows **no output at all**. No news is good news — if there's no error, the job is done.

```bash
cp /etc/hosts ~
```
Copies `/etc/hosts` into your home directory silently.

### Verbose Mode (`-v`)

```bash
cp -v /etc/hosts ~
```
Output: `'/etc/hosts' -> '/home/sysadmin/hosts'` — clearly shows what was copied and where.

### Renaming While Copying

If you give just a directory as the destination, the original filename is kept. To rename on the fly, add the new name to the destination path:

```bash
cp /etc/hosts ~/hosts.copy
```
Copies the file **and** saves it under the new name `hosts.copy`.

---

## The Overwrite Danger

By default, if the destination file already exists, `cp` overwrites it **without any warning**.

**Example:**
1. Copied `/etc/hostname` into `example.txt` (content: `localhost`)
2. Ran `cp /etc/timezone example.txt` again
3. Result: the old content is gone — `example.txt` now contains the new data (`Etc/UTC`)

### Solutions to Prevent Overwriting

**1. `-i` (Interactive Mode)**

Prompts before overwriting: `cp: overwrite 'example.txt'?`
- Type `y` → overwrite
- Type `n` → cancel

Limitation: tedious if copying 100+ existing files — you'd need to confirm each one individually.

**2. `-n` (No Clobber)**

Skips existing files entirely, without any prompt — never overwrites.

---

## Copying Directories

By default, `cp` only copies regular files — **not** directories. Trying to copy a directory directly gives an error:

```
cp: -r not specified; omitting directory '...'
```

### The Solution: Recursive Mode (`-r` or `-R`)

```bash
cp -r source_directory destination_directory
```

**Meaning of recursive:** Go into the folder → copy everything inside (files and sub-folders) → then go into those sub-folders too → replicate the entire tree structure.

---

#Linux #DevOps #CiscoNetworkingAcademy #LearningInPublic #BashScripting
