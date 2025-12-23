
## Module 4: Digesting Documentation

### Challenge: Learning From Documentation 

**Task:**

The goal of this challenge is to correctly run the program /challenge/challenge by providing the required command-line argument.

**Commands Used:**

```bash
ssh hacker@dojo.pwn.college
/challenge/challenge --giveflag
```

**Explanation:**

The challenge provided documentation stating that the program requires the --giveflag argument to run correctly. Running the program with this argument gives the flag.


**Output/Flag:**
```bash
pwn.college{Y7oTbVYP2RkBek85p7QtlCKcOh2.QX0ITO0wyN2MDM1EzW}
```

### Challenge: Learning Complex Usage

**Task:**

The goal of this challenge was to correctly use a program that requires an argument which itself takes another argument. Specifically, the program /challenge/challenge needed the --printfile option along with the path of the file to read in order to reveal the flag.

**Commands Used:**

```bash
ssh hacker@dojo.pwn.college
 /challenge/challenge --printfile /challenge/DESCRIPTION.md
/challenge/challenge --printfile /flag
```

**Explanation:**

This challenge focused on understanding commands that accept arguments which themselves require values. The documentation explained that the --printfile argument expects a file path as its parameter and will print the contents of that file.

Once the command was executed with both the argument and the correct file path, the program successfully printed the contents of /flag, revealing the flag.


**Output/Flag:**
```bash
pwn.college{cPBhRMYf9EMC-29aD3T7Me8qV9y.QX1ITO0wyN2MDM1EzW}
```

### Challenge: Reading Manuals 

**Task:**

The goal of this challenge was to use the man command to read the manual page of the challenge program and determine the correct option syntax required to print the flag.

**Commands Used:**

```bash
ssh hacker@dojo.pwn.college
 man challenge
/challenge/challenge --qmpqqu 489

```

**Explanation:**

This challenge focused on learning how to read manual pages using the man command. Instead of guessing program arguments, the correct usage was documented in the man page.

By examining the DESCRIPTION section of the manual, a hidden option --qmppqu was revealed. The documentation clearly stated that the flag would be printed only if this option was provided with the value 489.


**Output/Flag:**
```bash
 pwn.college{Y4qmBCp8pqum9zElGk93_JTqw7z.QX0EDO0wyN2MDM1EzW}
```
### Challenge: Searching Manuals 

**Task:**

This level focuses on searching within man pages to quickly locate required options. Instead of manually scrolling, the task is to use built-in search functionality of the man command to find the option that prints the flag.

**Commands Used:**

```bash
ssh hacker@dojo.pwn.college
 man challenge
/challenge/challenge --zqx

```

**Explanation:**

This challenge focused on learning how to search within manual pages using the man command instead of manually scrolling through long documentation.

After opening the manual page with man challenge, the built-in search feature (/) was used to locate relevant options inside the documentation. By searching for keywords related to flag output, a hidden option --zqx was discovered within the man page.


**Output/Flag:**
```bash
  pwn.college{U2_hHKAVBDAWeTCbz-Jitwcph-F.QX1EDO0wyN2MDM1EzW}
```
### Challenge: Searching For Manuals 

**Task:**

The objective of this challenge was to locate a hidden manual page for the /challenge/challenge program and use the information found in that manual to execute the program correctly and retrieve the flag.

**Commands Used:**

```bash
ssh hacker@dojo.pwn.college
 man man
man -k challenge
man cgimnxghzv
/challenge/challenge --cgimnx 152

```

**Explanation:**

First, the man man command was used to understand how to search for manual pages. Using this, man -k challenge was executed, which listed all man pages related to the keyword challenge. This revealed a randomly named manual page: cgimnxghzv.
Opening this man page provided the correct option and usage format required by /challenge/challenge.

**Output/Flag:**
```bash
  pwn.college{cIg1imnx5WTghz-vxXUjziTLkdj.QX2EDO0wyN2MDM1EzW}
```

### Challenge: Helpful Programs 

**Task:**

The objective of this challenge was to learn how to use a program’s built‑in help documentation (--help) to understand its available options, identify the correct usage, and execute the program properly to retrieve the flag.

**Commands Used:**

```bash
ssh hacker@dojo.pwn.college
/challenge/challenge --help
/challenge/challenge -g
/challenge/challenge -p
/challenge/challenge -g 953


```

**Explanation:**

When a program doesn't have a man page, the --help flag is the primary way to discover its functionality. By running the help command, I found that the program required a specific "secret value" passed via the -g flag. I used the -p (print-value) argument to reveal that the secret number was 953. Finally, executing the program with -g 953 validated the provided the flag.

**Output/Flag:**
```bash
 pwn.college{ECKWqWhXiypJ9TVXRGtxhwCMm5f.QX3IDO0wyN2MDM1EzW}
```
### Challenge: Help For Builtins

**Task:**

The objective of this challenge was to recognize that the challenge command is a shell builtin, not an external program, and to use the shell’s help system to find the correct arguments needed to retrieve the flag.

**Commands Used:**

```bash
ssh hacker@dojo.pwn.college
help challenge
challenge --secret AyFyv5e6

```

**Explanation:**

By executing help challenge, I was able to read the documentation for this specific builtin and identify that it required the --secret flag followed by a specific value: AyFyv5e6. Providing this value allowed the shell to process the builtin command successfully and display the flag.

**Output/Flag:**
```bash
 pwn.college{AyFyv5e6iQyE8fn15GqemrWsvSU.QX0ETO0wyN2MDM1EzW}
```
