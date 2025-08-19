# Bandit Level 10 → Level 11

## Goal
The password for the next level is stored in a file called `data.txt`, which contains base64-encoded data.

## Steps

1. **Connect via SSH**  
   ```bash
   ssh bandit10@bandit.labs.overthewire.org -p 2220
   ```

2. **List the directory contents**  
   ```bash
   ls
   ```
   Found a file named `data.txt`.

3. **Check file content**  
   ```bash
   cat data.txt
   ```
   The content was base64 encoded text.

4. **Decode base64**  
   To convert the base64 data into readable ASCII text:
   ```bash
   cat data.txt | base64 -d
   ```
   This revealed the password for the next level.

## Notes
- `base64 -d` decodes base64 to plain text.  
- This is a common method to hide or encode data in files.
