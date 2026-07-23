# Day 28 of Cisco Linux Essentials Course

Today I took a deep dive into Variables in Linux — instead of just memorizing commands, I focused on understanding how the Bash shell actually works under the hood.

## Local vs Environment Variables

**Local Variables** (`var=value`) are confined strictly to the current shell — child processes or new terminal tabs have zero awareness of them.

**Environment Variables** (`export VAR=value`) have a global scope and get passed down to child sub-processes.

Also practiced:
- `env | grep` — search for exported global variables
- `set` — lists everything, including local variables
- `unset` — resets/deletes a variable

## Understanding the $PATH Variable

Commands like `ls`, `cd`, or `date` aren't magic — they're actual executable binary files stored in directories like `/bin` or `/usr/bin`. The `$PATH` variable works like an address book: when you type a command, Bash searches every directory listed in `$PATH`, from left to right, separated by colons.

If a command fails with `bash: command not found`, it simply means Bash searched every directory in `$PATH` and couldn't find that executable anywhere.

## A Mistake Worth Knowing

Updating `$PATH` requires caution:

- **Wrong way:** `PATH=/my/custom/bin` — overwrites the entire address book, breaking basic system commands like `ls` and `cat`
- **Right way:** `PATH=/my/custom/bin:$PATH` (prepend) or `PATH=$PATH:/my/custom/bin` (append) — safely preserves existing system paths

Tested all of these scenarios hands-on on my AWS EC2 instance.

#Linux #DevOps #CiscoNetworkingAcademy #LearningInPublic #Bash
