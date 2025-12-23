
## Module 3: Comprehending Commands

### Challenge: Cat: not the pet, but the command!

**Task:**

This challenge focuses on understanding absolute paths in Linux and how the cat command can be used to read files that are not located in the current working directory.
**Commands Used:**

```bash
ssh hacker@dojo.pwn.college
cat flag

```
**Explanation:**

The cat command (short for concatenate) is one of the most critical Linux commands used to display the contents of files. In this challenge, the flag was automatically copied into a file named `flag` located in the user’s home directory.
Since the shell starts in the home directory by default. Running cat flag reads the contents of the file and prints them directly to the terminal.

**Output/Flag:**

```bash
pwn.college{UEqFzKMYpcTi-OW1dWMFhcXWCRH.QXxCTN0wyN2MDM1EzW}

```
### Challenge: Catting Absolute Paths

**Task:**

This challenge focuses on understanding absolute paths in Linux and how the cat command can be used to read files that are not located in the current working directory.

**Commands Used:**

```bash
ssh hacker@dojo.pwn.college
cat /flag

```
**Explanation:**

The flag file is located at /flag, which is outside the home directory. By using an absolute path that starts from the root directory (/), the cat command can directly access and display the file’s contents without depending on the current working directory.

**Output/Flag:**

```bash
pwn.college{OG-KTGOcXWjOOchKIVd8p9xZnsE.QX5ET00wyN2MDM1EzW}

```


### Challenge: More Catting Practice

**Task:**

The objective of this challenge was to retrieve the flag using the cat command while not being allowed to change directories. The flag was placed in an unknown location, requiring the use of an absolute path to access it.

**Commands Used:**

```bash
ssh hacker@dojo.pwn.college
cat /usr/share/initramfs-tools/flag

```
**Explanation:**

In this level, the cd command was disabled, so changing the working directory was not possible. To solve this, the challenge text provided the exact location of the flag: /usr/share/initramfs-tools/flag.By supplying this full absolute path to the cat command, the file could be accessed directly without changing directories. 

**Output:**

```bash
You cannot use the 'cd' command in this level, and must retrieve the flag by
absolute path. Plus, I hid the flag in a different directory! You can find it
in the file /usr/share/initramfs-tools/flag. Go cat it out **without** cding
into that directory!

pwn.college{sUuIDJk2OYRXfxp_mgVTVLrXAz.QXwIT00wyN2MDM1EzW}

```
**Flag:**

```bash
pwn.college{sUuIDJk2OYRXfxp_mgVTVLrXAz.QXwIT00wyN2MDM1EzW}

```

### Challenge: Grepping for a Needle in a Haystack

**Task:**

The objective of this challenge was to locate the flag hidden inside a very large text file. Since displaying the entire file using cat would be inefficient, the task required using the grep command to search for a specific pattern within the file.

**Commands Used:**

```bash
ssh hacker@dojo.pwn.college
grep pwn.college /challenge/data.txt
```
**Explanation:**

The challenge message indicated that the file /challenge/data.txt contained a large amount of text and that the flag always starts with pwn.college.
Instead of printing the full file, grep was used to search for lines containing the string pwn.college.

**Output/Flag:**

```bash
pwn.college{Y8MGSlQ-Bw6yi22qprry-ACF3Rz.QX3EDO0wyN2MDM1EzW}
```

### Challenge: Comparing Files

**Task:**

The goal of this challenge was to identify a single unique line (the real flag) hidden among two similar files. By using the diff command.


**Commands Used:**

```bash
ssh hacker@dojo.pwn.college
diff /challenge/decoys_only.txt /challenge/decoys_and_real.txt

```
**Explanation:**

Manually checking two large files for differences is inefficient. The diff command compares files line by line and highlights any changes between them.
By running diff on the two files, the output showed a line that exists only in the second file.

 Lines prefixed with > indicate content present in the second file but not in the first, which directly revealed the real flag.

**Output:**

```bash
89a90
> pwn.college{gWNpOOuuXWmioYpcDMD2foawW-E.01MwMDOxwyN2MDM1EzW}

```
**Flag:**

```bash
pwn.college{gWNpOOuuXWmioYpcDMD2foawW-E.01MwMDOxwyN2MDM1EzW}
```

### Challenge: Listing Files

**Task:**

The objective of this challenge was to discover and execute a file whose name had been randomly changed inside the /challenge directory. The challenge emphasizes using the ls command to explore directories when file names are not explicitly provided.

**Commands Used:**

```bash
ssh hacker@dojo.pwn.college
ls /challenge
/challenge/DESCRIPTION.md
/challenge/16444-renamed-run-10796

```
**Explanation:**

Manually guessing file names in a directory can be tedious and unreliable. The ls command is used to view the contents of a directory.

Running ls /challenge revealed two entries:
16444-renamed-run-10796  DESCRIPTION.md
Running /challenge/DESCRIPTION.md revealed that directory does not exist this confirmed that 16444-renamed-run-10796 correct randomized filename.

**Output:**

```bash
16444-renamed-run-10796  DESCRIPTION.md
bash: /challenge/DESCRIPTION.md: Not a directory
Yahaha, you found me! Here is your flag:
pwn.college{Q52cd9qisKJvahEQscdAnCPi8pc.QX4IDO0wyN2MDM1EzW}
```
**Flag:**

```bash
pwn.college{Q52cd9qisKJvahEQscdAnCPi8pc.QX4IDO0wyN2MDM1EzW}

```


### Challenge: Touching Files

**Task:**

The objective of this challenge was to create two empty files named pwn and college inside the /tmp directory using the touch command, and then execute /challenge/run to obtain the flag.

**Commands Used:**

```bash
cd /tmp
ls
touch pwn
touch college
/challenge/run

```
**Explanation:**

The touch command is used to create new, empty files.
Since writing to the root directory (/) is restricted the /tmp directory, however, is writable by regular users, making it the correct location for file creation.

After navigating to /tmp, two files—pwn and college—were successfully created. Once both required files existed, running /challenge/run verified their presence and printed the flag.

**Output:**
```bash
Success! Here is your flag:
pwn.college{MO1nMv23n0GdPz3eCLU3C7LIVYq.QXwMDO0wyN2MDM1EzW}
```
**Flag:**

```bash
pwn.college{MO1nMv23n0GdPz3eCLU3C7LIVYq.QXwMDO0wyN2MDM1EzW}

```

### Challenge: Removing Files

**Task:**

The objective of this challenge was to delete a file named delete_me from the home directory and then run a verification script to confirm its removal and retrieve the flag.

**Commands Used:**

```bash
ssh hacker@dojo.pwn.college
ls ~
rm delete_me
/challenge/check
 
```
**Explanation:**

The rm command is used to remove files in Linux.
First, the contents of the home directory were listed to confirm the presence of the delete_me file. Once verified, the file was deleted using rm delete_me.

After successfully removing the file, the /challenge/check program was executed. This script checked whether the file had been deleted correctly and, upon confirmation, displayed the flag.

**Output:**
```bash
Excellent removal. Here is your reward:
pwn.college{EyngHGupHa3c776rXs9TbYWilkg.QX2kDM1wyN2MDM1EzW}
```
**Flag:**

```bash
pwn.college{EyngHGupHa3c776rXs9TbYWilkg.QX2kDM1wyN2MDM1EzW}

```

### Challenge: Moving Files

**Task:**

The goal of this challenge was to move the /flag file to the location /tmp/hack-the-planet and then run a verification script to obtain the flag.

**Commands Used:**

```bash
ssh hacker@dojo.pwn.college
mv /flag /tmp/hack-the-planet
/challenge/check

 
```
**Explanation:**

The goal was to move the /flag file to the directory /tmp/hack-the-planet. Since the file was not in the current working directory, I used its absolute path to move it directly.
The mv command was used to relocate the file to the required directory. After completing the move, I ran the provided check command for the flag.

**Output:**
```bash
Congrats! You successfully moved the flag to /tmp/hack-the-planet!
pwn.college{szHKBviewSGs5MxDbyLW6B8eegn.OV0xEzNxwyN2MDM1EzW}

```
**Flag:**

```bash
pwn.college{szHKBviewSGs5MxDbyLW6B8eegn.OV0xEzNxwyN2MDM1EzW}

```
### Challenge: Copying Files

**Task:**

The objective of this challenge was to copy the /flag file into the directory /tmp/hack-the-planet without removing the original file,and then run a verification script to obtain the flag .

**Commands Used:**

```bash
ssh hacker@dojo.pwn.college
cp /flag /tmp/hack-the-planet
/challenge/check

 
```
**Explanation:**

The cp command was used to create a duplicate of the /flag file at the target location. Unlike mv, copying preserves the original file while placing a copy in the specified directory. After copying /flag into /tmp/hack-the-planet ,the verification script was then executed to confirm the copy operation and reveal the flag.

**Output:**
```bash
Congrats! You successfully copied the flag to /tmp/hack-the-planet! Here it is:
pwn.college{sWxgey03euHtnlgutd56Rb9WhjK.0lNxQTMywyN2MDM1EzW}

```
**Flag:**

```bash
pwn.college{sWxgey03euHtnlgutd56Rb9WhjK.0lNxQTMywyN2MDM1EzW}
```
### Challenge: Hidden Files

**Task:**

The goal of this challenge was to locate a hidden flag file in the root directory. The flag file was hidden using a dot (.) prefix, so it would not appear with normal directory listing commands.

**Commands Used:**

```bash
ssh hacker@dojo.pwn.college
ls /
ls -a /
cat /.flag-32048318421699
```
**Explanation:**

By default, the ls command does not display hidden files, which are files whose names start with a dot (.). After listing the root directory and not seeing the flag, I used ls -a / to show all files, including hidden ones. This revealed the hidden flag file. I then used cat with the file’s absolute path to read its contents.

**Output/Flag:**
```bash
pwn.college{EyCNb6upYoYiu0-KuxMLK4oQpHV.QXwUDO0wyN2MDM1EzW}
```
### Challenge: An Epic Filesystem Quest

**Task:**

The objective of this challenge was to navigate a series of directories following hidden clues to ultimately find a flag. The challenge contains basic Linux commands: cd for changing directories, ls for listing contents (including hidden files), and cat for reading file contents.

**Commands Used:**

```bash
cd /
ls
cat SECRET
cd /usr/share/games/fortunes
ls
cat SPOILER
cd /usr/lib/python3/dist-packages/twisted/internet/iocpreactor/__pycache__
ls
cat DOSSIER
cd /usr/share/m17n/icons
ls -a
cat .EVIDENCE
cd /usr/lib/python3/dist-packages/sage/combinat/matrices/__pycache__
ls
cat LEAD
cd /usr/share/racket/pkgs/plot-gui-lib/plot/private/gui/compiled
ls
cat DISPATCH
cd /opt/linux/linux-5.4/include/dt-bindings/leds
ls
cat README
cat /usr/local/lib/python3.8/dist-packages/numpy/random/_examples/cffi
ls /usr/local/lib/python3.8/dist-packages/numpy/random/_examples/cffi
cat /usr/local/lib/python3.8/dist-packages/numpy/random/_examples/cffi/TIP-TRAPPED
cd /usr/lib/x86_64-linux-gnu/gio
ls -a
cat .BLUEPRINT

```


**Output/Flag:**
```bash
pwn.college{MBNN2trCGlzR6FxaFDRBPl_e7Dv.QX5IDO0wyN2MDM1EzW}
```
### Challenge: Making Directories

**Task:**

The goal of this challenge was to create a directory named pwn inside /tmp, place a file named college in it, and then run /challenge/run to obtain the flag. This introduces the mkdir command for creating directories and demonstrates organizing files within them.

**Commands Used:**

```bash
cd /tmp
mkdir pwn
cd /tmp/pwn
touch college
/challenge/run

```
**Explanation:**

The mkdir command was used to create a new directory pwn in /tmp. After entering the directory with cd, the touch command created an empty file named college then  verification script was then executed to confirm the copy operation and reveal the flag .

**Output:**
```bash
Success! Here is your flag:
pwn.college{8Ox5OHEm5vrBf21RTjzzINiJYVK.QXxMDO0wyN2MDM1EzW}
```
**Flag:**
```bash
pwn.college{8Ox5OHEm5vrBf21RTjzzINiJYVK.QXxMDO0wyN2MDM1EzW}
```
### Challenge: Finding Files

**Task:**

The goal of this challenge was to locate a hidden flag somewhere on the filesystem. This introduces the find command, which allows searching for files and directories based on name, type, or other criteria.
**Commands Used:**

```bash
ssh hacker@dojo.pwn.college
find / -name flag
cat  /usr/local/lib/python3.8/dist-packages/pwnlib/flag
cat /usr/share/racket/pkgs/macro-debugger-text-lib/macro-debugger/analysis/private/flag

```
**Output/Flag:**
```bash
pwn.college{0LWA7EwTllcWWQZnm2RfL8g733b.QXyMDO0wyN2MDM1EzW}
```

### Challenge: Linking Files

**Task:**

In this challenge, the flag is stored in /flag, but the provided program /challenge/catflag does not read it directly. Instead, the program always attempts to read the file located at /home/hacker/not-the-flag.The task is to use symbolic links to redirect the program to the real flag without modifying the program itself.

**Commands Used:**

```bash
ssh hacker@dojo.pwn.college
ln -s /challenge/catflag /home/hacker/not-the-flag
cat /home/hacker/not-the-flag
cat /challenge/catflag

rm /home/hacker/not-the-flag
ln -s /flag /home/hacker/not-the-flag
/challenge/catflag

```
**Explanation:**

Initially, I created a symbolic link that pointed /home/hacker/not-the-flag to /challenge/catflag. This was a wrong approach because /challenge/catflag is a script that always tries to read /home/hacker/not-the-flag. Linking the script to itself caused it to loop without ever accessing the real flag.

 I realized that the correct approach was to replace /home/hacker/not-the-flag with a symbolic link pointing directly to /flag. Since /challenge/catflag blindly reads /home/hacker/not-the-flag, it followed the symlink and ended up reading /flag instead.

**Output/Flag:**
```bash
pwn.college{YzUqCNyW9P8LKlmsw4f0ZRxWTHt.QX5ETN1wyN2MDM1EzW}
```

