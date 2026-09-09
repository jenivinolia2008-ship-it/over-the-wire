# OverTheWire Bandit – Level 10

## Objective

The objective of Level 10 is to decode the contents of `data.txt`.

The file contains data encoded using **Base64**.

## Command

First, list the file:

```bash
ls
```

You will see:

```text
data.txt
```

Use the `base64` command to decode it:

```bash
base64 -d data.txt
```

## Explanation

* `base64` → Used to encode or decode Base64 data.
* `-d` → Means **decode**.
* `data.txt` → The file containing the encoded data.

So:

```bash
base64 -d data.txt
```

means:

**Decode the Base64 content stored in `data.txt`.**

The output is the **password for Level 11**.
