# OverTheWire Bandit – Level 0

## 🎯 Objective

The main objective of **Bandit Level 0** is to connect to the Bandit server using **SSH (Secure Shell)**.

---

## 🔹 Command

```bash
ssh bandit0@bandit.labs.overthewire.org -p 2220
```

---

## 🔹 Explanation of the Command

### 1. `ssh`

`ssh` stands for **Secure Shell**.

It is used to securely connect to a **remote server or computer**.

Example:

```bash
ssh username@server
```

---

### 2. `bandit0`

`bandit0` is the **username**.

We are logging into the Bandit server using the `bandit0` user account.

---

### 3. `@`

The `@` symbol separates the **username** from the **server address**.

```bash
bandit0@server
```

Meaning:

**Login as `bandit0` on that server.**

---

### 4. `bandit.labs.overthewire.org`

This is the **hostname/server address**.

It tells SSH which server we want to connect to.

---

### 5. `-p`

`-p` is used to specify the **port number**.

```bash
-p 2220
```

Here, SSH connects through **port 2220**.

---

## 🔹 Complete Meaning

```bash
ssh bandit0@bandit.labs.overthewire.org -p 2220
```

This means:

**Connect to the OverTheWire Bandit server as user `bandit0` using SSH through port `2220`.**

---

## 🔐 Password

The password for Level 0 is:

```text
bandit0
```

When you type a password in the terminal, **nothing will appear on the screen**.

This is normal.

Type the password and press **Enter**.

---

## ✅ Successful Login

After successful login, you will see something similar to:

```bash
bandit0@bandit:~$
```

### Meaning:

* `bandit0` → Current username
* `bandit` → Server name
* `~` → Home directory
* `$` → Normal user prompt

---

## 🧠 Important Points

1. `ssh` → Used to securely connect to a remote server.
2. `bandit0` → Username.
3. `bandit.labs.overthewire.org` → Server hostname.
4. `-p 2220` → Specifies port number 2220.
5. `bandit0` → Level 0 password.
6. Main concept of Level 0 → **SSH login**.

---

## ⭐ General SSH Syntax

```bash
ssh USERNAME@SERVER -p PORT
```

For Bandit Level 0:

```bash
ssh bandit0@bandit.labs.overthewire.org -p 2220
```

### Short Remembering Trick

**SSH → Username → Server → Port**

```text
ssh → bandit0 → bandit server → 2220
```
