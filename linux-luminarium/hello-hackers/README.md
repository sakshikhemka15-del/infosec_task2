

## Module 1: Hello Hackers

### Challenge: Intro To Commands

**Task:**

The goal of this challenge is to learn how to connect to the Linux Luminarium environment using SSH and run a basic Linux command to get the flag.

**Commands Used:**

```bash
ssh hacker@dojo.pwn.college
hello
```

**Explanation:**

To solve this challenge, an SSH connection is made to the Linux Luminarium server. Since the server uses key-based authentication, the SSH public key must first be added to the pwn.college account.

After successfully connecting using the ssh command, a Linux shell is provided where commands can be executed. The challenge requires running the hello command exactly as given. Linux commands are case-sensitive, so correct spelling is important. 

**Output:**

```bash
Success! Here is your flag:
pwn.college{gu_nYFIEvzXaRvZiJyCR-pXzLj-.QX3YjM1wiM1IzNxEzW}

```
**Flag:**

```bash
pwn.college{Q6eV3wAV1cMzJkmSpwiZJWiPdbq.QX3YjM1wyN2MDM1EzW}
```
---



### Challenge: Intro To Arguments

**Task:**

This challenge focuses on understanding how Linux commands take arguments and how the shell interprets user input.


**Commands Used:**

```bash
ssh hacker@dojo.pwn.college
hello hackers
```
**Explanation:**

After connecting to the environment using SSH, commands can be executed in the Linux shell. In Linux, the first word entered is treated as the command, and any words after it are treated as arguments.
In this challenge, the hello command must be run with a single argument, hackers.
 
**Output:**

```bash
Success! Here is your flag:
pwn.college{Q9HJa8BtWjzdChjPxDE9KWtFeiR.QX4YjM1wyN2MDM1EzW}
```
**Flag:**
```bash
pwn.college{Q9HJa8BtWjzdChjPxDE9KWtFeiR.QX4YjM1wyN2MDM1EzW}
```

---
### Challenge: Command History

**Task:**

The goal of this challenge is to understand how the Linux shell saves previously executed commands and allows them to be reused.

**Commands Used:**

```bash
ssh hacker@dojo.pwn.college
# Use the Up Arrow key
```

**Explanation:**

The Linux shell automatically stores executed commands so they can be reused without typing them again. This challenge places the flag directly into the saved command list.By using the Up Arrow key, earlier commands can be accessed and check where flag is located.

**Output:**

```bash
the flag is pwn.college{Q_LvdxssjCm3bQP3ENL1210ZHeI.0lNzEzNxwyN2MDM1EzW}
```

**Flag:**
```bash
pwn.college{Q_LvdxssjCm3bQP3ENL1210ZHeI.0lNzEzNxwyN2MDM1EzW}
```

---


