# OverTheWire Bandit – Level 1

## Objective

The objective of Level 1 is to find the password stored in a file named `-` in the home directory.

## Command

```bash
ls
```

This command lists the files and directories in the current directory.

The output will show:

```text
-
```

## Problem

Normally, we use `cat` to display the contents of a file:

```bash
cat filename
```

But here the filename is `-`.

If we use:

```bash
cat -
```

`-` is treated as standard input instead of a filename.

## Solution

Use:

```bash
cat ./-
```

### Explanation

* `cat` → Displays the contents of a file.
* `./` → Refers to the current directory.
* `-` → The name of the file.

So:

```bash
cat ./-
```

means:

**Display the contents of the file named `-` in the current directory.**

The output is the **password for Level 2**.
