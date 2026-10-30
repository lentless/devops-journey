# Day-07 (Linux: File Management and vim)

## What I learned

- `rmdir` removes only empty directories. `rm -rf dir` deletes a directory and everything in it with no undo, so check the path first.
- `cp` copies a file into a new file (overwrites if the name exists). Directories need `cp -r`.
- `mv` renames or moves. If the target is a directory, the file goes inside it. If the target is an existing file, it is overwritten.
- vim means "Vi IMproved", an enhanced version of vi. As a normal user install it with `sudo apt install vim`.
- vim has 3 main modes: normal (default, keys are commands), insert (typing text), and command (starts with `:`).
- I open vim from the terminal (`vim file`). Everything after that is typed inside vim. Keys in normal mode act immediately. `:` commands need Enter.
- Navigation: `gg` first line, `G` last line, `:500` jumps to line 500.
- Editing: `o` new line below, `O` new line above, `u` undo, `Ctrl+r` redo, `dd` delete line.
- Saving: `:wq` save and quit, `:q!` quit without saving.
- Reading files: `less` pages through a file, `head` shows the first lines, `tail` shows the last lines, `tail -f` follows a file live (useful for logs).
- `echo` prints text. `>` redirects it into a file and overwrites. `>>` appends.

## Commands/syntax practiced

- `ls`, `cd`, `mkdir`, `rmdir`, `touch`
- `rm file`, `rm -rf dir`
- `cp file new_name`, `mv old new`
- `vim file`, `sudo apt install vim`
- vim: `i`, `Esc`, `:wq`, `:q!`, `:500`, `gg`, `G`, `o`, `O`, `u`, `dd`
- `less file`, `head -n 10 file`, `tail -n 20 file`
- `echo "text" > file`, `echo "text" >> file`

## What confused me

- Where do the ESC commands get typed? Inside vim after it is open. Esc is a key that returns to normal mode, then I type the command. `:` commands need Enter.
- Where is `echo` used? It prints text. With `>` or `>>` it writes that text into a file without opening an editor, which is common in scripts and pipelines.
