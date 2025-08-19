# Bandit Level 12 → Level 13 Solution

We are given a file called **data.txt**, which is a **hexdump** of a file that has been repeatedly compressed.  
The task is to revert it back step by step until we get readable text (the password).  

---

## Steps

1. **Create a temporary working directory**  
   ```bash
   mktemp -d
   cd /tmp/tmp.XXXXXX    # or the created folder name
   ```

2. **Copy and rename the file**  
   ```bash
   cp ~/data.txt .
   mv data.txt data
   ```

3. **Reverse the hexdump**  
   ```bash
   xxd -r data data
   ```

---

## Decompression by File Type

Use the `file data` command after each step to see the current format. Then apply the correct decompression:

### 🔹 gzip compressed data
```bash
mv data data.gz
gunzip data.gz
# New file will again be named "data"
```

### 🔹 bzip2 compressed data
```bash
mv data data.bz2
bzip2 -d data.bz2
```

### 🔹 XZ / LZMA compressed data
```bash
mv data data.xz
xz -d data.xz
```

### 🔹 POSIX tar archive (or “tar archive”)
```bash
mkdir t
tar -xf data -C t
# Only one file will be extracted
mv t/* ./data
rm -r t
```

### 🔹 ASCII text / plain text
```bash
cat data
```

---

## Repeat Until Password is Found

Keep repeating this cycle:
1. Run `file data`
2. Apply the matching decompression command
3. Rename to `data` again
4. Continue…

Eventually, the last `cat data` will reveal the **password for Level 13** 🎯
