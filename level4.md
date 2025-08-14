# Bandit Level 4 → Level 5

## Steps
1. Connect to the server:
   ```bash
   ssh bandit4@bandit.labs.overthewire.org -p 2220
   ```
2. List files in the home directory:
   ```bash
   ls
   ```
   Found a directory named `inhere`.
3. Enter the `inhere` directory:
   ```bash
   cd inhere
   ```
4. This directory contains files named `-file00` to `-file09`.
5. Attempting to open the first couple of files showed unreadable binary data.
6. Check the file types for all files:
   ```bash
   file ./*
   ```
   The output shows that `./-file07` is in ASCII text format (human-readable).
7. Display the contents of the ASCII file:
   ```bash
   cat ./-file07
   ```
   This reveals the password for the next level (hidden here for security).

## Notes / Learnings
- Learned how to identify file formats using the `file` command.
- ASCII files contain human-readable text, while other types may be binary.
- Files with names starting with a dash should be accessed with `./` prefix to avoid confusion with command options.
- Important: Passwords are hidden for security and should not be shared publicly.
