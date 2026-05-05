---
title: Basic commands
nav_order: 2
parent: Information server   # optional grouping
---

# Basic server commands (Linux)

This page lists common commands to navigate on a server, manage files, and understand permissions.

---

## Opening a terminal and pasting

- **Copy** text: usually `Ctrl + Shift + C` (or just select text, depending on your terminal)
- **Paste** text into the terminal:
  - Often: `Ctrl + Shift + V`
  - In many terminal apps: **right mouse button** (right-click) pastes
  - Sometimes: middle mouse button (mouse wheel click) pastes

{: .warning }
Be careful when pasting commands from anywhere (email, chat, web). Always read the command before pressing **Enter**.

---

## Where am I? (navigation)

### Show current directory
```bash
pwd
```

### List files
```bash
ls
ls -l      # long view (permissions, owner, size, date)
ls -lah    # long view + human-readable sizes + show hidden files
```

### Change directory
```bash
cd /path/to/somewhere
cd ..      # go one directory up
cd -       # go back to the previous directory
cd ~       # go to your home directory
```

{:  .note    }
Tab completion (very useful). Start typing a path/filename and press **Tab** to auto-complete. And double tab to see options to complete. 

---

## Creating directories and files

### Create a directory
```bash
mkdir my_folder
mkdir -p projects/2026-05-05_project1/results   # create nested folders if needed
```

### Create an empty file
```bash
touch notes.txt
```

---

## Copy, move, rename, delete

### Copy files
```bash
cp file1.txt copy_of_file1.txt
cp file1.txt /path/to/destination/
```

Copy a directory (and everything inside):
```bash
cp -r my_folder my_folder_backup
```

### Move / rename
`mv` is used for both moving and renaming.

Rename a file:
```bash
mv oldname.txt newname.txt
```

Move a file to another directory:
```bash
mv myfile.txt /path/to/destination/
```

### Delete (be careful)
Delete a file:
```bash
rm myfile.txt
```

Delete a directory (and everything inside):
```bash
rm -r my_folder
```

{: .warning }
`rm` permanently deletes files (there is usually no “Recycle Bin” on servers). Double-check before running `rm -r`.

---

## Viewing file contents

Show a short text file:
```bash
cat file.txt
```

View long files page-by-page:
```bash
less file.txt
```

Useful inside `less`:
- `q` = quit
- `/word` = search for "word"
- `n` = next match

Show the first / last lines:
```bash
head file.txt
tail file.txt
tail -f logfile.txt   # follow a file that is growing (logs)
```

---

## Searching

Search for a file by name (in the current directory and below):
```bash
find . -name "*.fastq.gz"
```

Search for text inside files:
```bash
grep "ERROR" logfile.txt
grep -R "some_text" .   # recursive search in all files under current directory
```

---

## Permissions (who can read/write/execute)

### Read permissions with `ls -l`
Example output:
```bash
ls -l
# -rw-r----- 1 user group  1200 May  5  file.txt
# drwxr-x--- 2 user group  4096 May  5  my_folder
```

The permission string has 3 blocks:
- **user** (owner)
- **group**
- **others** (everyone else)

And 3 permission types:
- `r` = read (see file contents / list directory)
- `w` = write (edit file / create/delete inside directory)
- `x` = execute (run a program / enter a directory)

### Changing permissions with `chmod`

Make a script executable:
```bash
chmod +x myscript.sh
```

Remove write permission for others:
```bash
chmod o-w file.txt
```

(Advanced) numeric mode example:
```bash
chmod 640 file.txt
# 6 = rw- (user)
# 4 = r-- (group)
# 0 = --- (others)
```

### Changing owner/group (often restricted)
```bash
chown user file.txt
chgrp group file.txt
chown user:group file.txt
```
On many servers, only admins can change owners.

---

## Ownership: who owns a file?

```bash
ls -l file.txt
```

If you see permission problems (“Permission denied”), check:
- Are you in the right directory?
- Do you have write permission where you are trying to create/edit?
- Is the file owned by someone else or a different group?

---

## Helpful “safety” tips

- Prefer `cp` for safety when you’re unsure; use `mv` when you’re confident.
- Use `ls` before and after a command to confirm what changed.
- Avoid spaces in file/folder names; use `_` instead (e.g. `raw_data_2026`).

---

## Quick cheat sheet

```bash
pwd                  # where am I
ls -lah              # list files (detailed)
cd <dir>             # go to directory
mkdir -p <dir>       # create directory (nested ok)
cp <src> <dst>       # copy
mv <src> <dst>       # move/rename
rm <file>            # delete file
rm -r <dir>          # delete directory (danger)
less <file>          # view file
grep -R "text" .     # search text in files
find . -name "*.txt" # find by name
chmod +x <file>      # make executable
```