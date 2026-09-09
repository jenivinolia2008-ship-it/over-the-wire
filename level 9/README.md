# OverTheWire Bandit – Level 9

## Objective

The objective of Level 9 is to find the password in `data.txt`.

The password is stored among **human-readable strings**, and it is preceded by several `=` characters.

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
strings data.txt | grep "==="
```

## Explanation

* `strings data.txt` → Extracts readable text from the file.
* `|` → Passes the output of `strings` to the next command.
* `grep "==="` → Searches for lines containing `===`.

The command:

```bash
strings data.txt | grep "==="
```

finds the readable text containing `===`.

The password is the readable text shown in the output.

**That is the password for Level 10.**
