# Day-05 (Linux Fundamentals + Linux Folder Structure)

## What I learned

### Video 1: Operating System Fundamentals

- A computer system = hardware + software. The OS is software that sits
  BETWEEN them, managing hardware so other software doesn't have to talk
  to it directly (OS mediates/bridges — it doesn't "consist of" hardware
  and software itself)
- Hardware: CPU, storage, memory, etc. Software: the apps running on top
- OS core functions: process management, device management, memory
  management, network management
- Linux structure: kernel (talks directly to hardware) + system
  libraries + shell/CLI (and optionally GUI)
- Correction: Linux CAN have a GUI (Ubuntu Desktop, GNOME, etc.) — it's
  not CLI-only. Servers specifically run WITHOUT a GUI on purpose: no
  monitor attached, GUI wastes CPU/RAM on rendering, and CLI enables
  scripting/automation. This is a deliberate DevOps choice, not a Linux
  limitation
- Linux distributions: Ubuntu, Fedora, Debian, Alpine, Red Hat, etc.
  (using WSL Ubuntu)
- Package managers automate the full software lifecycle: finding
  packages, resolving and installing dependencies automatically,
  updating, and removing cleanly — instead of doing all of that by hand
- Different distros use different package managers: apt (Ubuntu/Debian),
  yum/dnf (RedHat/Fedora), apk (Alpine)
- Key distinction (common interview question): `apt update` only
  refreshes the local list of what's available — installs nothing.
  `apt upgrade` actually installs newer versions of what's on the system

### Video 2: Linux Folder Structure

- Two user types: root (full administrative access) vs normal user
  (limited, granted access)
- Shell prompt structure: `user@hostname:path$` for normal users,
  `user@hostname:path#` for root — `$` vs `#` signals which one you are
- `~` vs `/` — different things entirely:
  - `/` = root of the ENTIRE filesystem, the single starting point every
    folder branches from
  - `~` = shortcut meaning "my home directory," but WHOSE home depends
    on who's logged in. For normal user kiit, `~` = `/home/kiit`. For
    root, `~` = `/root` (NOT `/home/root` — root gets its own dedicated
    home folder directly under `/`)
- Switch to root: `sudo -i` or `sudo su -`
- Back to normal user: `exit`, `Ctrl+D`, or `su - username`
- Top-level folders (seen via `cd /` then `ls -ltr`):
  - `/bin` — essential commands everyone needs (ls, cp, cat)
  - `/sbin` — essential admin-only commands (reboot, networking config)
  - `/usr` — most installed software/libraries actually live here
    (despite the name, stands for "Unix System Resources," not "user")
  - `/lib` — shared library files that binaries in bin/sbin depend on
  - `/etc` — system-wide config files
  - `/var` — frequently-changing data: logs, caches
  - `/tmp` — temporary files, cleared on reboot
  - `/home` — normal users' personal folders
  - `/root` — root's own separate home directory

## Commands/syntax practiced

- `apt install`, `apt list`, `apt update`, `apt upgrade`
- `sudo -i`, `sudo su -`, `exit`, `Ctrl+D`, `su - username`
- `cd /`, `ls -ltr`, `cd ~`

## What confused me

- `~` vs `/` — resolved: `/` is the fixed filesystem root, `~` is a
  per-user shortcut to that specific user's home directory, which
  differs between root and normal users
