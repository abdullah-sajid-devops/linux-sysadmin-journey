# Day 31 of Cisco Linux Essentials Course

Today I wrapped up Chapter 5 (The Linux Command Line) in NDG Linux Essentials, scoring **90%** on the assessment.

## Command Substitution
Using `$(command)` to embed command outputs dynamically into other commands — a modern, cleaner approach than legacy backticks.

## Quoting & Escaping Rules
- **Single Quotes (`'...'`)** — Strong suppression. Treats every special character (`$`, `*`, backtick) as literal text.
- **Double Quotes (`"..."`)** — Protects wildcards while still allowing variables and command substitution to execute.
- **Backslash (`\`)** — Escapes individual special characters when you don't want to quote the entire string.

## Control Statements for Execution Flow
- `;` — Sequential execution (runs regardless of success/failure)
- `&&` — Logical AND (runs the next command only if the previous one succeeds)
- `||` — Logical OR (runs the next command only if the previous one fails — fallback/error handling)

Small daily steps lead to big milestones. Next stop: Chapter 6.

#Linux #DevOps #CiscoNetworkingAcademy #LearningInPublic #Bash
