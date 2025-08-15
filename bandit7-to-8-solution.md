Bandit Level 7 → Level 8 Solution (no spoilers)

- **Objective:** Find the password for Bandit Level 7, stored in `data.txt` next to the word `millionth`.

- **Steps:**
  1. SSH into the Bandit server:
     ```bash
     ssh bandit6@bandit.labs.overthewire.org -p 2220
     ```
  2. List the files in the current directory to locate `data.txt`:
     ```bash
     ls
     ```
  3. (Optional) Open the file to inspect its contents:
     ```bash
     cat data.txt
     ```
  4. Search for the target word `millionth` to quickly find the password:
     ```bash
     grep "millionth" data.txt
     ```

- **Notes:**  
  - `grep` is more efficient than scrolling through the file manually.
  - The password appears **next to the word `millionth`**.