# OverTheWire Bandit – Level 5

## Objective

The objective of Level 5 is to find the password stored in a file inside the `inhere` directory.

The correct file has these properties:

* Human-readable
* 1033 bytes in size
* Not executable

## Command

First, enter the directory:

```bash
cd inhere
```

Then use:

```bash
find . -type f -size 1033c ! -executable
```

## Explanation

* `find .` → Searches from the current directory.
* `-type f` → Searches only for regular files.
* `-size 1033c` → Finds files with exactly 1033 bytes.
* `! -executable` → Excludes executable files.

The command will show the path of the correct file.

Then use:

```bash
cat ./path
```

Replace `./path` with the path returned by `find`.

The output is the **password for Level 6**.
