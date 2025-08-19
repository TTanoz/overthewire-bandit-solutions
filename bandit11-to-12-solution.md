# Bandit Level 11 → 12 Solution

**Objective**  
The password for the next level is stored in the file `data.txt`, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions (ROT13).

---

**Steps Taken**  

1. Connected to the server with SSH:  
   ```bash
   ssh bandit11@bandit.labs.overthewire.org -p 2220
   ```

2. Listed the directory contents and found `data.txt`:  
   ```bash
   ls
   ```

3. Displayed the file, but the content appeared as unreadable scrambled text:  
   ```bash
   cat data.txt
   ```

4. Since the text was ROT13 encoded, I decoded it using the `tr` command:  
   ```bash
   cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
   ```

5. The decoded output revealed the password for Level 12.

---

**Password**  
*(Hidden — no spoilers)*
