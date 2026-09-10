# OverTheWire Bandit – Level 12

## Goal

The password for the next level is stored in `data.txt`.

However, the file is a **hex dump** of a file that has been compressed multiple times using different compression methods.

The task is to convert the hex dump back to its original binary form and then repeatedly identify and decompress the file until the password is obtained.

---

## Step 1: Login to Bandit Level 12

```bash
ssh bandit12@bandit.labs.overthewire.org -p 2220
```

Enter the password obtained from Level 11.

---

## Step 2: Check the File

```bash
ls
```

Output:

```text
data.txt
```

Check the file type:

```bash
file data.txt
```

Output:

```text
data.txt: ASCII text
```

The file is an ASCII text file containing a **hex dump**.

---

## Step 3: Create a Temporary Directory

It is better to work in `/tmp` because the Bandit home directory does not allow us to create new files.

```bash
cd /tmp
mkdir jenifer
cd jenifer
```

Copy the original file:

```bash
cp ~/data.txt .
```

---

## Step 4: Convert the Hex Dump Back to Binary

Use `xxd`:

```bash
xxd -r data.txt data
```

Check the file type:

```bash
file data
```

Output:

```text
data: gzip compressed data
```

The file is compressed using **gzip**.

---

## Step 5: Decompress the Gzip File

Rename the file:

```bash
mv data data.gz
```

Decompress:

```bash
gzip -d data.gz
```

Check the file:

```bash
file data
```

Output:

```text
data: bzip2 compressed data
```

The next compression method is **bzip2**.

---

## Step 6: Decompress the Bzip2 File

Rename:

```bash
mv data data.bz2
```

Decompress:

```bash
bzip2 -d data.bz2
```

Check:

```bash
file data
```

Output:

```text
data: gzip compressed data
```

---

## Step 7: Decompress Gzip Again

Rename:

```bash
mv data data.gz
```

Decompress:

```bash
gzip -d data.gz
```

Check:

```bash
file data
```

Output:

```text
data: POSIX tar archive (GNU)
```

The file is now a **tar archive**.

---

## Step 8: Extract the Tar Archive

```bash
tar -xf data
```

Check the files:

```bash
ls
```

A new file called:

```text
data5.bin
```

is created.

Check its type:

```bash
file data5.bin
```

Output:

```text
data5.bin: POSIX tar archive (GNU)
```

---

## Step 9: Extract `data5.bin`

```bash
tar -xf data5.bin
```

Check:

```bash
ls
```

A new file called:

```text
data6.bin
```

is created.

Check:

```bash
file data6.bin
```

Output:

```text
data6.bin: bzip2 compressed data
```

---

## Step 10: Decompress `data6.bin`

Rename:

```bash
mv data6.bin data6.bz2
```

Decompress:

```bash
bzip2 -d data6.bz2
```

Check:

```bash
file data6
```

Output:

```text
data6: POSIX tar archive (GNU)
```

---

## Step 11: Extract `data6`

```bash
tar -xf data6
```

Check:

```bash
ls
```

A new file called:

```text
data8.bin
```

is created.

Check:

```bash
file data8.bin
```

Output:

```text
data8.bin: gzip compressed data
```

---

## Step 12: Decompress `data8.bin`

Rename:

```bash
mv data8.bin data8.gz
```

Decompress:

```bash
gzip -d data8.gz
```

Check:

```bash
file data8
```

Output:

```text
data8: ASCII text
```

Now the file contains normal text.

---

## Step 13: Read the Password

```bash
cat data8
```

The output is the **password for Bandit Level 13**.

---

## Important Commands Used

| Command    | Purpose                          |
| ---------- | -------------------------------- |
| `file`     | Identifies the actual file type  |
| `xxd -r`   | Converts hex dump back to binary |
| `mv`       | Renames a file                   |
| `gzip -d`  | Decompresses gzip files          |
| `bzip2 -d` | Decompresses bzip2 files         |
| `tar -xf`  | Extracts tar archives            |
| `ls`       | Lists files                      |
| `cat`      | Displays file contents           |
| `cp`       | Copies a file                    |
| `mkdir`    | Creates a directory              |

## Main Concept

The important idea in Level 12 is:

```text
Hex Dump
   ↓
xxd -r
   ↓
Gzip
   ↓
Bzip2
   ↓
Gzip
   ↓
Tar
   ↓
Tar
   ↓
Bzip2
   ↓
Tar
   ↓
Gzip
   ↓
ASCII Text
   ↓
cat
   ↓
Password for Level 13
```

### Key Lesson

Do not assume the file type from its filename.

Use:

```bash
file filename
```

after every extraction or decompression to identify what to do next.
