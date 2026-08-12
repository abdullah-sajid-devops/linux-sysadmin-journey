# Day 43 of Cisco Linux Essentials Course

Started Chapter 9 today, focused on archiving and compression. Also took the Midterm Exam covering Modules 1-9, scoring **75% (30/40)**.

## Archiving vs Compression — Two Different Concepts

These sound similar but solve completely different problems.

**Archiving** takes a bunch of separate files and bundles them into a single file or location. It's purely organizational — it does not reduce file size at all. It just packages multiple files together so they're easier to move, store, or share as one unit.

**Compression** takes a large file and shrinks its actual size. A file that's thousands of MB can be compressed down to just a few KB, depending on the content and algorithm used. This saves storage space and reduces transfer time.

**Key distinction:** You can archive without compressing, and you can compress without archiving — they're independent operations, though they're often used together.

## Compression Tools

- `gzip` — one of the most common Linux compression tools, produces `.gz` files
- `bzip2` — generally compresses better than gzip, but slower
- `xz` — offers the best compression ratio among the three, at the cost of more processing time

## Archiving Tool: `tar`

`tar` (Tape Archive) is the standard Linux tool for bundling multiple files/directories into a single archive file.

### The Three Operation Modes

| Flag | Mode | Purpose |
|---|---|---|
| `-c` | Create | Builds a new archive |
| `-x` | Extract | Pulls files back out of an archive |
| `-t` | List | Shows the contents of an archive without extracting |

### Mandatory Options for Creating an Archive

When creating an archive, `-f` (specifying the archive filename) must be used alongside `-c`. Without `-f`, `tar` won't know what to name the output file.

Example structure:
```bash
tar -cf archive_name.tar file1 file2 file3
```

### Extracting an Archive

```bash
tar -xf archive_name.tar
```

## ZIP Files

Unlike `tar`, which only archives (you need a separate compression tool like `gzip` to shrink it), `zip` does **both** by default — it archives multiple files into one and compresses them in the same step. This is why `.zip` is such a common, self-contained format across both Linux and Windows.

## Midterm Exam — Modules 1-9

Scored 75% (30/40) on the midterm covering everything from Module 1 through Module 9. A good checkpoint — shows solid overall grasp, with a few specific areas worth revisiting before moving further into the course.

#Linux #DevOps #CiscoNetworkingAcademy #LearningInPublic #SysAdmin  
