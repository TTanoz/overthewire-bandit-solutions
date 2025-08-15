# Bandit Level 5 → 6 Solution

**Goal:**  
Find a file somewhere under the `inhere` directory that is **human-readable**, **1033 bytes in size**, and **not executable**.  
The file contains the password for the next level.

---

## 1. Understanding the requirements
- **human-readable** → ASCII or plain text
- **1033 bytes in size** → exactly 1033 bytes (`c` = bytes)
- **not executable** → file does not have execute permissions

---

## 2. Finding the correct file

Run the following command:

```bash
find ./inhere -type f -size 1033c ! -executable
```

**Explanation:**
- `find` → search for files
- `./inhere` → search in the `inhere` directory
- `-type f` → only files
- `-size 1033c` → exactly 1033 bytes (`c` means bytes)
- `! -executable` → file should not be executable

**Example output:**
```
./inhere/maybehere07/.file2
```

---

## 3. Reading the file

To safely read the file (especially if it starts with a dash or dot in the name):

```bash
cat -- ./inhere/maybehere07/.file2
```

The `--` tells `cat` to stop parsing options, ensuring the filename is treated literally.

---

## 4. Getting the password
The output will be a single line of text with no spaces — that is the password for the next level.

---

## 5. Logging into the next level

```bash
ssh bandit6@bandit.labs.overthewire.org -p 2220
```
When prompted, paste the password you just found.

---

✅ **Tip:** Using `find` with filters saves time by avoiding the need to check every file manually.
