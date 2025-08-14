# OverTheWire Bandit — Level 1

## Task
Connect to the Bandit server via SSH and find the file containing the next level’s password.

## Steps Taken
1. Connect to the server:
```bash
ssh bandit1@bandit.labs.overthewire.org -p 2220
```

2. List files in the home directory:
```bash
ls
```
Output:
```
-
```

3. Attempt to go to the previous directory:
```bash
cd -
```
- This did not work as expected because `OLDPWD` was not set.

4. Display the contents of the tricky file using `./-`:
```bash
cat ./-
```
Output:
```
[PASSWORD HIDDEN]
```

## Notes / Learnings
- Learned how to handle files with unusual names (`-`).  
- Practiced using `cat ./-` to access files starting with a dash.  
- Important: Passwords are hidden for security and should not be shared publicly.
