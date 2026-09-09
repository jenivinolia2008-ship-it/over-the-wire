# OverTheWire Bandit – Level 2

## Objective

The objective of Level 2 is to find the password stored in a file named **`spaces in this filename`**.

## Command

First, list the files:

```bash
ls
```

The output will show:

```text
spaces in this filename
```

## Problem

The filename contains **spaces**.

If we use:

```bash
cat spaces in this filename
```

the terminal treats each word as a separate argument.

## Solution

Use:

```bash
cat "spaces in this filename"
```

## Explanation

* `cat` → Displays the contents of a file.
* `" "` → Keeps the entire filename together as one argument.
* `spaces in this filename` → The complete filename.

So:

```bash
cat "spaces in this filename"
```

means:

**Display the contents of the file named `spaces in this filename`.**

The output is the **password for Level 3**.
