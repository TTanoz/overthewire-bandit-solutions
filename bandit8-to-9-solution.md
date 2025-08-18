# Bandit Level 8 → Level 9 Solution (no spoilers)

**Objective:**  
Find the password for the next level. It is stored in `data.txt`, and it is the only line that occurs exactly once.

---

## 1. SSH into the Bandit server
```bash
ssh bandit8@bandit.labs.overthewire.org -p 2220
```

---

## 2. Locate the file
List the files in the current directory to confirm the presence of `data.txt`:
```bash
ls
```

---

## 3. Inspect the file (optional)
You can view the file with `cat`, but it is very long:
```bash
cat data.txt
```

---

## 4. Find the unique line
Since the file is large, use `sort` and `uniq` to identify the line that appears only once:
```bash
sort data.txt | uniq -u
```

This command sorts the file and then filters only the unique line. That line is the password for the next level.

---

## 5. Log into the next level
```bash
ssh bandit9@bandit.labs.overthewire.org -p 2220
```

When prompted, paste the password you found.
