# OverTheWire Bandit — Level 2

## Task
Connect to the Bandit server via SSH and find the file containing the next level’s password.

## Steps Taken
1. Connect to the server:
```bash
ssh bandit2@bandit.labs.overthewire.org -p 2220
```

2. List files in the home directory:
```bash
ls
```
Output:
```
--spaces in this filename--
```

3. Attempt to go to the previous directory:
```bash
cat "--spaces in this filename--"
```
- This did not work as expected because Bash interpreted the `--` at the beginning of the filename as an option.


4. Display the contents of the tricky file using `cat -- "--spaces in this filename--"`
```bash
cat -- "--spaces in this filename--"
```
Output:
```
[PASSWORD HIDDEN]
```

## Notes / Learnings
- Learned how to handle files with spaces in their names.
- Learned how to handle files starting with `--` by using `--` to separate options from filenames.
- Practiced using `cat -- "filename"` to access such tricky files.
- Important: Passwords are hidden for security and should not be shared publicly.

