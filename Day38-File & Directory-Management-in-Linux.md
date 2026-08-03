# Day 38 - Linux Essentials (Cisco)

## File & Directory Management in Linux (CLI)

Managing files and directories through the Linux Command Line Interface (CLI) is where the real power of Linux comes from. Before moving further, there are two important concepts that you should always remember.

---

# Linux is Case Sensitive

Linux treats uppercase and lowercase letters as completely different characters.

For example:

```bash
hello.txt
Hello.txt
HELLO.txt
```

Although these filenames look similar, Linux considers them **three different files**.

Always be careful while creating files, running commands, or writing scripts because even a single uppercase or lowercase letter can completely change the result.

---

# UTF-8 & ASCII Standards

Linux uses the **UTF-8** character encoding standard, which is based on the **ASCII** standard.

UTF-8 allows Linux to support thousands of different characters and languages while remaining compatible with traditional ASCII characters.

---

# What is Globbing (Wildcards)?

Globbing is one of the most useful features of the Bash shell.

Wildcards are special characters that help the shell create **filename matching patterns**.

Instead of working on one file at a time, you can use a pattern to target hundreds or even thousands of files with a single command.

This makes Bash scripting much faster and more efficient.

The most commonly used wildcard characters are:

- `*` (Asterisk)
- `?` (Question Mark)
- `[]` (Brackets)
- `!` (Negation)

---

# Asterisk (*) Character

### Rule

The asterisk (`*`) represents **zero or more characters**.

In simple words, it matches anything after the specified pattern.

---

## Example 1

```bash
echo /etc/t*
```

Shows every file inside the `/etc` directory whose name starts with the letter **t**.

It doesn't matter what comes after **t**, or even if nothing comes after it.

---

## Example 2

```bash
echo /etc/*.d
```

Displays every file that ends with the `.d` extension.

---

## Example 3

```bash
echo /etc/r*.conf
```

Matches every file that starts with **r** and ends with `.conf`.

---

# Question Mark (?) Character

### Rule

The question mark (`?`) represents **exactly one character**.

Unlike the asterisk, it does **not** match multiple characters.

---

## Example 1

```bash
echo /etc/t???????
```

Matches files that start with **t** and contain exactly **seven more characters** after it.

In other words, the filename must contain **8 characters** in total.

---

## Example 2

```bash
echo /etc/*.???
```

Matches files whose extension contains exactly **three characters**.

For example:

```text
.net
.gen
.txt
```

---

## Example 3

```bash
echo /etc/*????????????????????
```

Finds filenames that are at least **20 characters long**.

Here:

- `*` matches zero or more characters.
- Twenty `?` characters ensure the filename has at least twenty additional characters.

---

# Bracket [] Characters

Brackets allow you to match **specific characters** or **character ranges**.

---

## Specific Character Selection

When you place multiple characters inside brackets, Bash matches **any one** of those characters.

Example:

```bash
echo /etc/[gu]*
```

This command displays every file inside `/etc` that starts with either:

- `g`
- `u`

The `*` means the filename can contain any number of additional characters after the first letter.

---

# Character Ranges

Instead of writing every character individually, you can specify a range by using a hyphen (`-`).

## Alphabet Range

```bash
echo /etc/[a-d]*
```

Matches every file whose name starts with:

- a
- b
- c
- d

---

## Number Range

```bash
echo /etc/*[0-9]*
```

Matches every filename that contains **at least one number** anywhere in its name.

The first `*` allows any characters before the number, while the last `*` allows any characters after the number.

# Exclamation Point (!) Character (Negation)

The exclamation mark (`!`) is used for **negation**.

When you place `!` at the beginning of a bracket expression, Bash excludes the characters or ranges written inside the brackets.

Instead of matching them, it matches everything **except** them.

---

## Excluding Specific Characters

```bash
echo /etc/[!DP]*
```

This command displays every file inside the `/etc` directory that **does not** start with **D** or **P**.

Any filename starting with any other character will be matched.

---

## Excluding a Character Range

```bash
echo /etc/[!a-t]*
```

This command displays every file inside `/etc` whose name **does not** start with any letter from **a** to **t**.

The output may include files starting with:

- u
- v
- w
- x
- y
- z

It can also include filenames that begin with uppercase letters or numbers.

For example:

```text
/etc/ucf.conf
/etc/vim
/etc/X11
```

---

## Pro Tip

For the Cisco Linux Essentials exam, remember that bracket negation is usually written with an exclamation mark (`!`).

Example:

```bash
[!0-9]
```

Some Linux shells also support the caret (`^`) symbol.

Example:

```bash
[^0-9]
```

Both patterns perform the same task, but throughout this course we mainly focus on using `!`.

---

# ls Command and Globbing

When learning Bash wildcards, most examples use the `echo` command.

With `echo`, wildcard expansion looks simple and easy to understand.

However, things become a little confusing when you replace `echo` with the `ls` command.

This is one of the most important concepts beginners should understand.

---

# How ls Behaves

The `ls` command behaves differently depending on what you pass as its argument.

---

## When the Argument is a File

Example:

```bash
ls /etc/adduser.conf
```

Since the argument is a regular file, `ls` simply displays that file's name or its details (depending on the options you use).

---

## When the Argument is a Directory

Example:

```bash
ls /etc/apparmor
```

This is where many beginners get confused.

Instead of displaying the directory's own name, `ls` lists **everything inside that directory**.

In other words, it opens the directory and shows its contents.

---

# The Real Confusion

Consider the following command:

```bash
ls /etc/ap*
```

Before `ls` runs, Bash expands the wildcard.

The shell may convert it into something like this:

```text
/etc/apparmor
/etc/apparmor.d
/etc/apt
```

Since all three are directories, `ls` doesn't print their names.

Instead, it opens each directory and lists everything inside them.

The result is often a long and messy output, making it difficult to understand which files belong to which directory.

---

# The Solution: -d Option

To avoid this confusion, Linux provides the `-d` option.

### Purpose

The `-d` flag tells `ls`:

> "Don't show me what's inside the directory. Just display the directory's own name."

Example:

```bash
ls -d /etc/ap*
```

Now the output simply becomes:

```text
/etc/apparmor
/etc/apparmor.d
/etc/apt
```

This makes wildcard expansion much easier to understand.

---

# Copying Files (cp Command)

The `cp` command is used to copy files and directories in Linux.

Its basic syntax is:

```bash
cp source destination
```

Where:

- **Source** → The file you want to copy.
- **Destination** → The location (or new filename) where you want the copy to be created.

---

# The Silence Rule

One interesting thing about Linux is that many commands follow a simple rule:

> **No news is good news.**

If the `cp` command completes successfully, it usually doesn't display any output.

Example:

```bash
cp /etc/hosts ~
```

If no error appears, it simply means the file has been copied successfully.

---

# Verbose Mode (-v)

Sometimes you may want Linux to tell you exactly what was copied.

For that, use the **verbose** option.

```bash
cp -v /etc/hosts ~
```

Example output:

```text
'/etc/hosts' -> '/home/sysadmin/hosts'
```

This clearly shows the source file and its destination.

---

# Renaming While Copying

One useful feature of the `cp` command is that you can rename a file while copying it.

This saves you from running the `mv` command afterward.

Example:

```bash
cp /etc/hosts ~/hosts.copy
```

The original file remains unchanged, while the copied file is saved with a new name.

Result:

```text
hosts.copy
```

This is a simple but very useful feature that can save time during everyday Linux administration.

# Overwriting Files in Linux

By default, the `cp` command overwrites an existing file without displaying any warning.

If a file with the same name already exists at the destination, its old content will be replaced by the new one.

This behavior is known as **overwriting**.

---

## Example

Suppose you first copy the `hostname` file:

```bash
cp /etc/hostname example.txt
```

Now `example.txt` contains:

```text
localhost
```

Later, you run another command:

```bash
cp /etc/timezone example.txt
```

The previous content is completely replaced.

Now the file contains:

```text
Etc/UTC
```

The original data is gone because `cp` overwrote the existing file.

---

# Protecting Yourself from Overwriting

Linux provides multiple options to prevent accidental data loss.

The two most commonly used options are:

- `-i` (Interactive Mode)
- `-n` (No Clobber)

---

# Interactive Mode (-i)

The `-i` option tells Linux to ask for confirmation before replacing an existing file.

Instead of overwriting immediately, the terminal displays a prompt.

Example:

```bash
cp -i /etc/timezone example.txt
```

Output:

```text
cp: overwrite 'example.txt'?
```

You can respond with:

- `y` → Yes, overwrite the file.
- `n` → No, keep the existing file.

This option is very useful when copying only a few files.

However, imagine copying hundreds of files.

Linux will ask for confirmation **for every single file**, which quickly becomes frustrating and time-consuming.

---

# No Clobber (-n)

The `-n` option stands for **No Clobber**.

In Linux, **clobber** means replacing or destroying an existing file.

With `-n`, the `cp` command simply skips any file that already exists.

It does **not** overwrite the file, and it does **not** ask for confirmation.

Example:

```bash
cp -n /etc/timezone example.txt
```

If `example.txt` already exists, Linux silently ignores it and moves on.

This option is especially useful when copying large numbers of files and you want to keep every existing file safe.

---

# Copying Directories

By default, the `cp` command copies **regular files only**.

Directories are not copied automatically.

If you try to copy a directory without using any additional option, Linux returns an error.

Example:

```bash
cp Documents Backup
```

Output:

```text
cp: -r not specified; omitting directory 'Documents'
```

This message simply means that Linux skipped the directory because recursive mode was not enabled.

---

# Recursive Copy (-r / -R)

To copy an entire directory, including all of its files and subdirectories, you must enable **recursive mode**.

Linux provides two options:

```bash
-r
```

or

```bash
-R
```

Both options perform the same task.

Example:

```bash
cp -r Documents Backup
```

or

```bash
cp -R Documents Backup
```

---

## What Does Recursive Mean?

Recursive means that Linux doesn't stop at the main folder.

Instead, it enters the directory and copies:

- Every file
- Every subdirectory
- Every file inside those subdirectories
- Every folder inside those folders

It continues this process until the entire directory structure has been copied.

In simple words, recursive mode creates a complete copy of the directory tree.

---

# Key Takeaways

Throughout this lesson, we covered some of the most important Linux file management concepts.

✔ Linux is case-sensitive.

✔ Linux uses the UTF-8 character encoding standard, which is based on ASCII.

✔ Bash Globbing allows you to match filenames using wildcard characters.

✔ `*` matches zero or more characters.

✔ `?` matches exactly one character.

✔ `[]` matches specific characters or character ranges.

✔ `[!]` excludes specific characters or ranges.

✔ The `ls` command behaves differently for files and directories.

✔ The `-d` option displays the directory itself instead of its contents.

✔ The `cp` command copies files.

✔ The `-v` option shows exactly what has been copied.

✔ You can rename a file while copying it.

✔ The `-i` option asks before overwriting an existing file.

✔ The `-n` option prevents overwriting existing files.

✔ The `-r` and `-R` options copy entire directories recursively.

---

# Conclusion

Understanding these concepts is essential for anyone learning Linux or Bash scripting.

Wildcard patterns make file management much faster, while the `cp` command gives you complete control over copying files and directories safely.

Mastering these commands will help you work more efficiently in the Linux terminal and build a strong foundation for shell scripting, system administration, and DevOps.
