#Day 02

## What I learned

- touch is to create an empty file, vim/vi is to create file where we can write shell script
- touch is used in automation as vim/vi opens an interactive editor
- when the vim/vi file is opened then its in normal to make it in insert press "i" and after editing press ESC and then
  :wq! to save and exit or :q! to exit without saving
- man <command> opens the manual for any other command
- Shebang #!/bin/bash-bash is executable, the first script witten in the shell script,other options include bash, sh, dash, ksh
- #!/bin/bash vs #!/bin/sh, sometimes sh redirect to bash or dash based on the ubuntu machine intalled in the machine
- echo prints the text directly and cat is to print the content of the file
- Two ways to run a script:
  1. `sh filename.sh` — runs directly through the shell, no permission needed
  2. `./filename.sh` — runs as its own program, needs execute permission
- Permissions = three sets of three (`rwx rwx rwx`) → Owner / Group / Others.
  r=4, w=2, x=1, add up per group for the digit. `chmod 755` = owner full
  control, group & others can read/run only. `chmod +x` just adds execute —
  safer than `777`, which gives everyone full access and is a real interview
  red flag, not a "correct" fix

## Commands/syntax practiced

- `touch`, `vim`/`vi`, `man <cmd>`, `echo`, `cat`
- `chmod +x filename.sh`, `chmod 755`, `chmod 777`
- `pwd`, `mkdir`, `rm -rf`
- Health checks: `nproc`, `free -g`, `df -h`, `top`

## What confused me

- Owner/Group/Others and the r/w/x → digit mapping — clear now: three groups
  of three, each group's digit is read+write+execute added up (4+2+1)
- Why `#!/bin/sh` and `#!/bin/bash` behave differently — now understand
  `/bin/sh` is often just a symlink, so it varies by machine

## Tomorrow

- Video 2: `ps -ef`, `grep`, and process-related commands
