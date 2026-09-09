# OverTheWire Bandit – Level 6

## Objective

The objective of Level 6 is to find the password stored **somewhere on the server**.

The correct file has these properties:

* Owned by user `bandit7`
* Owned by group `bandit6`
* Exactly 33 bytes in size

## Command

Use the following command:

```bash
find / -user bandit7 -group bandit6 -size 33c 2>/dev/null
```

## Explanation

* `find /` → Searches from the root directory.
* `-user bandit7` → Finds files owned by user `bandit7`.
* `-group bandit6` → Finds files belonging to group `bandit6`.
* `-size 33c` → Finds files that are exactly 33 bytes.
* `2>/dev/null` → Hides permission-denied error messages.

The command will show the path of the correct file.

Then use:

```bash
cat /path/to/file
```

Replace `/path/to/file` with the path returned by the `find` command.

The output is the **password for Level 7**.
