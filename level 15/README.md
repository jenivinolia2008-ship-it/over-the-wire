# OverTheWire Bandit – Level 15

## Goal

The password for the next level can be retrieved by sending the current level's password to **localhost on port 30001 using SSL/TLS encryption**.

---

## Step 1: Login to Bandit Level 15

```bash
ssh bandit15@bandit.labs.overthewire.org -p 2220
```

Enter the password obtained from **Level 14**.

---

## Step 2: Connect using SSL/TLS

Use the following command:

```bash
openssl s_client -connect localhost:30001
```

This creates a secure SSL/TLS connection to port `30001`.

---

## Step 3: Enter the Current Password

After running the command, the terminal will show SSL connection information.

At the bottom, type the **Level 15 password** obtained from Level 14 and press **Enter**.

If the password is correct, the server will return the password for **Level 16**.

---

## Important Command

```bash
openssl s_client -connect localhost:30001
```

### Meaning

* `openssl` → Tool used for SSL/TLS operations.
* `s_client` → Creates an SSL/TLS client connection.
* `-connect` → Specifies the server and port to connect to.
* `localhost` → The same Bandit server.
* `30001` → The port used by this level.

---

## What I Learned

* `localhost` refers to the current machine/server.
* Ports identify different network services.
* SSL/TLS provides an encrypted connection.
* `openssl s_client` can be used to communicate with an SSL/TLS server.
* The password must be sent through the secure connection to obtain the next level's password.

---

## Short Notes

**Level 15 → Level 16**

```text
Login to bandit15
       ↓
Connect to localhost:30001
       ↓
Use SSL/TLS
       ↓
openssl s_client
       ↓
Enter Level 15 password
       ↓
Receive Level 16 password
```
