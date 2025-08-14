# OverTheWire Bandit — Level 0

## Task
Connect to the Bandit server via SSH and find the file containing the next level’s password.

## Steps Taken
1. Connect to the server:
```bash
ssh bandit0@bandit.labs.overthewire.org -p 2220
```

2. List files in the home directory:
```bash
ls
```
Output:
```
readme
```

3. Display the file contents:
```bash
cat readme
```
Output:
```
Congratulations on your first steps into the bandit game!!
Please make sure you have read the rules at https://overthewire.org/rules/
If you are following a course, workshop, walkthrough or other educational activity,
please inform the instructor about the rules as well and encourage them to
contribute to the OverTheWire community so we can keep these games free!

The password you are looking for is: [PASSWORD HIDDEN]
```

## Notes / Learnings
- Practiced SSH connection with a custom port (`-p 2220`).
- Learned to list files (`ls`) and read file contents (`cat`).
- Important: Never share actual Bandit passwords publicly in repositories.
