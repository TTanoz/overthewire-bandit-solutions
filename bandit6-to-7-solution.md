# Bandit Level 6 → 7 Solution

**Goal:**  
Find the password for the next level. The file has the following properties:
- Owned by user `bandit7`
- Group `bandit6`
- Exactly 33 bytes in size

---

## 1. Understanding the requirements
- **Owner** → `bandit7`
- **Group** → `bandit6`
- **Size** → 33 bytes (`c` = bytes)

---

## 2. Searching for the file

Start with the current directory:
```bash
find . -type f -user bandit7 -group bandit6 -size 33c
```

- `.` → search in the current directory and subdirectories
- `-type f` → only files
- `-user bandit7` → owner is bandit7
- `-group bandit6` → group is bandit6
- `-size 33c` → file size is 33 bytes

> ⚠️ If no results are found, you may need to expand the search to the root directory `/`.

```bash
cd /
find . -type f -user bandit7 -group bandit6 -size 33c
```

---

## 3. Locating the password file

From the results, you might see something like:
```
./var/lib/dpkg/info/bandit7.password
```

---

## 4. Reading the password

Use `cat` to display the content:
```bash
cat ./var/lib/dpkg/info/bandit7.password
```

The output is the **password for Bandit level 7**.

---

✅ **Tip:** Using `find` with **user, group, and size filters** is an efficient way to locate Bandit passwords without manually checking each file.
