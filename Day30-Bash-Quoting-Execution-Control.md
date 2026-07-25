# Day 30 of Cisco Linux Essentials Course

Today I dove deep into Chapter 5, focusing on how the Bash shell parses commands and controls execution flow.

## Quoting Mechanics

**Double Quotes (`" "`)** — Weak quotes. Suppress glob characters (`*`, `?`) while still allowing variable expansion (`$VAR`) and command substitution.

**Single Quotes (`' '`)** — Strong quotes. Treat every character as literal text, blocking all variables and substitutions.

**Backslash (`\`)** — Escape character. Acts like a single-character quote for fine-grained control over special characters.

**Backticks / `$(command)`** — Enables command substitution, executing an embedded command inline.

## Execution Control Operators

- **Semicolon (`;`)** — Unconditional execution. Runs commands sequentially regardless of success/failure.
- **Double Ampersand (`&&`)** — Logical AND. Runs the next command only if the previous one succeeds (exit status 0).
  Example: `sudo apt update && sudo apt upgrade -y`
- **Double Pipe (`||`)** — Logical OR. Runs the next command only if the previous one fails — acts as a fallback/error handler.

Building a strong foundation in terminal control, environment variables, and execution logic before moving deeper into Docker and Infrastructure as Code.

#Linux #DevOps #CiscoNetworkingAcademy #LearningInPublic #Bash
