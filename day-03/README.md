# Day-03

## What I learned

- Scripts should start with a metadata comment block right after the
  shebang: author, date, version, description
- Two ways to run multiple commands (df -h, free -g, nproc) with visible
  separation: manual `echo` labels before each, or `set -x` (debug mode,
  prints each command before running it)
- `ps -ef` lists every running process on the machine
- Pipe (`|`) sends the output of one command into the next command as input
- `grep "pattern"` filters which ROWS match; `awk -F" " '{print $2}'`
  extracts a specific COLUMN from each line (change $2 to $4 for the 4th
  field, etc.) — different jobs, often chained together
- Interview Q: why does `date | echo "hello"` only print "hello"? Because
  `echo` never reads from stdin at all — it only prints its literal
  argument, regardless of what's piped into it
- `set -euo pipefail` at the top of every script = exit on any error
  (`-e`), exit if a pipeline fails even mid-pipe (`-o pipefail`), treat
  unset variables as errors (`-u`). `set -x` is a separate, optional
  debug flag, not required alongside these
- Remote log files: `curl <url>` prints content to the screen (pipeable,
  e.g. `curl <url> | grep error`); `wget <url>` downloads and saves the
  file locally instead — that's the core difference between the two
- `sudo su -` switches to the root (admin) user
- `kill <PID>` sends a signal to a process (needs a process ID number,
  not a name — `pkill name` kills by name directly)
- `trap` is written INSIDE a script to catch a signal it receives and run
  custom cleanup instead of dying instantly
- Key fact: `kill -9` (SIGKILL) can NEVER be trapped — it's a forced,
  immediate kill. A plain `kill` (SIGTERM) CAN be trapped, which is why
  scripts use `trap` for graceful shutdown but have no defense against -9

## Commands/syntax practiced

- `df -h`, `free -g`, `nproc`, `set -x`
- `ps -ef`, `grep`, `awk -F" " '{print $2}'`, pipe (`|`)
- `set -euo pipefail`
- `curl <url>`, `curl <url> | grep error`, `wget <url>`
- `sudo su -`, `kill <PID>`, `pkill name`, `trap`
- if/else, for loops (started)

## What confused me

- trap vs kill vs signals — resolved: kill sends a signal, trap catches
  one inside a script, and SIGKILL (-9) specifically can never be caught

## Tomorrow

- More on if/else, for loops, and trap in practice
