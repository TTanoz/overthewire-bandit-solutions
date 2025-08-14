# Bandit Level 3 → Level 4

## Steps
1. Connect to the server:
   ```bash
   ssh bandit3@bandit.labs.overthewire.org -p 2220
   ```
2. List files in the home directory:
   ```bash
   ls
   ```
   Output shows a directory named `inhere`.
3. Change into the `inhere` directory:
   ```bash
   cd inhere
   ```
4. Listing files normally shows nothing, so check for hidden files:
   ```bash
   ls -a
   ```
   Found a file named `...Hiding-From-You`.
5. Display the contents of the file:
   ```bash
   cat ...Hiding-From-You
   ```
   This reveals the password for the next level (hidden here for security).

## Notes / Learnings
- Learned to check for hidden files using `ls -a`.
- Hidden files in Linux start with a dot (`.`) and will not appear in normal `ls` output.
- File names starting with multiple dots are still valid and can be accessed directly.
- Important: Passwords are hidden for security and should not be shared publicly.
