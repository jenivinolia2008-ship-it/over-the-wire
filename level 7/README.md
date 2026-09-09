# OverTheWire Bandit – Level 7

## Objective

The objective of Level 7 is to find the password in a file called `data.txt`.

The password is located next to the word **`millionth`**.

## Command

First, check the file:

```bash
ls
```

You will see:

```text
data.txt
```

Use the `grep` command:

```bash
grep millionth data.txt
```

## Explanation

* `grep` → Searches for specific text inside a file.
* `millionth` → The word we are searching for.
* `data.txt` → The file where we search.

The command:

```bash
grep millionth data.txt
```

searches for the word `millionth` in `data.txt` and displays the line containing it.

The text after `millionth` is the **password for Level 8**.
