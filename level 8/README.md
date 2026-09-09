# OverTheWire Bandit – Level 8

## Objective

The objective of Level 8 is to find the **only line that occurs once** in the file `data.txt`.

## Command

First, list the file:

```bash
ls
```

You will see:

```text
data.txt
```

Use:

```bash
sort data.txt | uniq -u
```

## Explanation

* `sort data.txt` → Sorts all the lines in `data.txt`.
* `|` → Sends the output of one command to the next command.
* `uniq -u` → Displays only the lines that occur **exactly once**.

So:

```bash
sort data.txt | uniq -u
```

means:

**Sort the file and find the line that appears only once.**

The output is the **password for Level 9**.
