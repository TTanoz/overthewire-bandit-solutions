# Bandit Level 9 → Level 10 Solution

## Steps Taken

1.  Logged into the Bandit game using SSH:

    ``` bash
    ssh bandit9@bandit.labs.overthewire.org -p 2220
    ```

2.  Listed the files in the home directory and found a file named
    `data.txt`:

    ``` bash
    ls
    ```

3.  Tried to read the file using `cat`, but the content was not in a
    human-readable format:

    ``` bash
    cat data.txt
    ```

4.  Attempted to search for the `=` character directly with grep:

    ``` bash
    grep "=" data.txt
    ```

    This returned the message:

        grep: data.txt: binary file matches

5.  Since the file contained binary data, used the `strings` command to
    extract human-readable text, then filtered with `grep` to find the
    line containing `=`:

    ``` bash
    strings data.txt | grep "="
    ```

6.  This revealed the password for the next level.

## Summary

The password for **Bandit Level 10** was hidden inside a binary file. By
combining `strings` and `grep`, the password was successfully extracted.
