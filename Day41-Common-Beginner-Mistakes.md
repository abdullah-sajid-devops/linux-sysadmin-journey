# Day 41 — Common Beginner Mistakes in Linux

Instead of a new topic today, sharing a few genuine mistakes I've made over the past 41 days of learning Linux — hopefully this saves someone else the same headache.

## 1. Running `rm` Without Thinking Twice

Coming from Windows, I assumed there'd be some kind of undo or Recycle Bin. There isn't. `rm` deletes files permanently and instantly. Now I always use `rm -i` when I'm not 100% sure, so it asks for confirmation before deleting.

## 2. Trying to `cp` a Directory and Getting Confused by the Error

Kept getting `cp: -r not specified; omitting directory` and didn't understand why. `cp` only copies files by default — directories need the `-r` (recursive) flag to copy everything inside them.

## 3. Not Realizing `cp` Overwrites Silently

Copied a file into a location where a same-named file already existed — it got overwritten with zero warning. Now I use `-i` (asks before overwriting) or `-n` (never overwrites) depending on the situation.

## 4. Forgetting Linux Is Case-Sensitive

`File.txt` and `file.txt` are two completely different files to Linux. This tripped me up more than once when a command "wasn't working" — it was just looking for a filename that technically didn't exist because of a capital letter.

## 5. Using `ls` With a Wildcard and Getting a Messy Output

Running `ls /etc/ap*` when it matches multiple directories doesn't just list their names — it dumps the entire contents of each one onto the screen. Fix: add `-d` to just get the directory names.

## Takeaway

None of these mistakes were serious, but each one taught me something no amount of just reading documentation would have. Making mistakes on a test server is genuinely one of the best ways to learn this stuff.

#Linux #DevOps #CiscoNetworkingAcademy #LearningInPublic #BeginnerMistakes
