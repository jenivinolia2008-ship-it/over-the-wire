# OverTheWire Bandit – Level 13

## Objective

The goal of Level 13 is to use the **SSH private key** provided in the home directory to log in as the `bandit14` user.

## Step 1: List the Files

```bash
ls
```

The file `sshkey.private` is present.

## Step 2: View the Private Key

```bash
cat sshkey.private
```

This displays the SSH private key.

**Note:** Never share a real private key with anyone.

## Step 3: Exit the Bandit Server

The SSH connection from Level 13 cannot be used to directly connect to Level 14 from the same server because connections from localhost are blocked.

```bash
exit
```

This returns to the local terminal.

## Step 4: Save the Private Key Locally

Open Git Bash and create a file:

```bash
nano sshkey.private
```

Paste the private key into the file.

Save and exit:

```text
Ctrl + O
Enter
Ctrl + X
```

## Step 5: Set the Correct Permission

```bash
chmod 600 sshkey.private
```

This gives the owner permission to read and write the private key while restricting access from others.

## Step 6: Login as bandit14

```bash
ssh -i sshkey.private bandit14@bandit.labs.overthewire.org -p 2220
```

Here:

* `ssh` → Starts an SSH connection.
* `-i sshkey.private` → Uses the specified private key.
* `bandit14@...` → Connects as the `bandit14` user.
* `-p 2220` → Connects through port `2220`.

If the connection is successful:

```bash
bandit14@bandit:~$
```

appears.

Therefore, **Level 13 is completed and Level 14 has started.**

---

# Level 13 → Level 14 Summary

```text
Level 13
   ↓
ls
   ↓
Find sshkey.private
   ↓
cat sshkey.private
   ↓
exit
   ↓
Save private key locally
   ↓
chmod 600 sshkey.private
   ↓
SSH using private key
   ↓
Login as bandit14
   ↓
Level 14
```

## Main Concept

**Level 13 teaches how to use an SSH private key for authentication instead of a password.**

The private key is used to authenticate the `bandit14` user and gain access to the next level.
