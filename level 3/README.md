# OverTheWire Bandit – Level 3

## Objective

The objective of Level 3 is to find the password stored in a **hidden file** inside the `inhere` directory.

## Command

First, list the files:

```bash
ls
```

You will see:

```text
inhere
```

Move into the directory:

```bash
cd inhere
```

`cd` is used to **change the current directory**.

Now list all files, including hidden files:

```bash
ls -a
```

You will see a hidden file:

```text
.hidden
```

## Solution

Use:

```bash
cat .hidden
```

## Explanation

* `ls` → Lists files and directories.
* `cd inhere` → Enters the `inhere` directory.
* `ls -a` → Lists all files, including hidden files.
* `.hidden` → Name of the hidden file.
* `cat .hidden` → Displays the contents of the hidden file.

The output is the **password for Level 4**.
