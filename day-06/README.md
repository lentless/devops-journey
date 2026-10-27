# Day-06 (Linux: User Management and SSH)

## What I learned

- User management gives each person their own account and permissions, so access can be role based (devs, QA, etc.).
- Users are listed in `/etc/passwd`, one line each: `name:x:UID:GID:comment:home:shell`. The `x` means the password hash lives in `/etc/shadow`.
- Passwords are stored as salted hashes, not encrypted, so nobody can decrypt them, not even root. A forgotten password can't be recovered, but root can reset it with `sudo passwd username`.
- `useradd` is low level and good for scripts. It doesn't create a home directory unless `-m` is used. `adduser` (Debian/Ubuntu) is an interactive wrapper that creates the home directory and asks for user details. It is a separate command, not the same options.
- `userdel username` deletes the user but keeps the home directory. `userdel -r` removes it too.
- Groups: `groupadd`, `/etc/group` format is `name:x:GID:members`. `usermod -aG group user` appends the user to a group. Without `-a` it replaces all other groups.
- SSH: the client (`ssh` command, included in Git Bash) runs on my machine. The server side is `sshd`, a daemon on the VM listening on port 22. Login is `ssh username@public-ip`. Cloud VMs often use a key file instead of a password.
- `sudo su -` gives a root shell if the user has sudo rights.

## Commands/syntax practiced

- `sudo useradd username` / `adduser username` / `userdel username`
- `cat /etc/passwd`, `sudo cat /etc/shadow`, `cat /etc/group`
- `sudo passwd username`
- `su - username`, `whoami` (current user, not location; `pwd` shows location)
- `groupadd groupname`, `usermod -aG groupname username`
- `ssh username@public-ip`
- `uname -a` (kernel, hostname, architecture)
- `sudo apt install vim`
- `sudo systemctl restart ssh`

## What confused me

- What is `/etc/ssh/sshd_config.d/60-cloudimg-settings.conf`? It's a drop-in config shipped with cloud images. On Ubuntu it usually sets `PasswordAuthentication no`, which blocks password logins (keys only). Setting it to `yes` allows passwords.
- Why `sudo systemctl restart ssh`? sshd reads its config only at start, so edits don't apply until the service restarts. Test with `sudo sshd -t` first and keep one session open.
