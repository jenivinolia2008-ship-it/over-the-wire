# OverTheWire Bandit – Level 11

## Objective

The objective of Level 11 is to decode the password in `data.txt`.

The text has been encoded using the **ROT13** method.

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
cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
```

## Explanation

* `cat data.txt` → Displays the contents of `data.txt`.
* `|` → Sends the output to the next command.
* `tr` → Translates characters from one set to another.
* `'A-Za-z'` → All uppercase and lowercase English letters.
* `'N-ZA-Mn-za-m'` → ROT13 character mapping.

ROT13 replaces each letter with the letter **13 positions away** in the alphabet.

So:

```bash
cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
```

decodes the ROT13 text.

The output is the **password for Level 12**.
