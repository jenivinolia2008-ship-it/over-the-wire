# OverTheWire Bandit – Level 4

## Objective

The objective of Level 4 is to find the password stored in the **only human-readable file** inside the `inhere` directory.

## Command

First, enter the directory:

```bash
cd inhere
```

List the files:

```bash
ls
```

You will see several files such as:

```text
-file00
-file01
-file02
...
-file09
```

These files contain different types of data. We need to find the one that contains readable text.

## Solution

Use the `file` command:

```bash
file ./*
```

The `file` command identifies the **type of each file**.

Look for the file that is identified as **ASCII text**.

Then use:

```bash
cat ./filename
```

Replace `filename` with the name of the ASCII text file.

For example:

```bash
cat ./-file07
```

## Explanation

* `cd inhere` → Enters the `inhere` directory.
* `ls` → Lists the files.
* `file ./*` → Checks the type of every file.
* `ASCII text` → Indicates a human-readable text file.
* `cat ./-file07` → Displays the contents of that file.

The output is the **password for Level 5**.
