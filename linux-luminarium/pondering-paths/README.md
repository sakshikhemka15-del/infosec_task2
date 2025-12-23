## Module 2: Pondering Paths

### Challenge: The Root

**Task:**

The goal of this challenge is to understand the Linux root directory and how to execute a program using its absolute path to retrieve the flag.

**Commands Used:**

```bash
ssh hacker@dojo.pwn.college
/pwn
```
**Explanation:**

In Linux, the filesystem starts at the root directory /. Programs can be executed by specifying their full path, known as an absolute path.In this challenge, a program named pwn is located directly inside the root directory. 

**Output:**

```bash
BOOM!!!
Here is your flag:
pwn.college{4olp4q8B07wCSrp_bl5V1NdkrQx.QX4cT00wyN2MDM1EzW}
```

**Flag:**
```bash
pwn.college{4olp4q8B07wCSrp_bl5V1NdkrQx.QX4cT00wyN2MDM1EzW}
```


### Challenge: Program and Absolute Paths

**Task:**
The goal of this challenge is to execute a program using its absolute path in order to retrieve the flag.

**Commands Used:**
```bash
ssh hacker@dojo.pwn.college
/challenge/run
```
**Explanation:**

In Linux, programs can be executed by specifying their full path, called an absolute path. In this challenge, the program run is located inside the /challenge directory, which is directly under the root directory /.
By providing the complete path /challenge/run, the system is able to locate and execute the program correctly.

**Output:**
```bash
Correct!!
/challenge/run is an absolute path! Here is your flag:
pwn.college{OKduHK2HtDP0eZRHP1mbZtSrVk0.QXlQTN0wyN2MDM1EzW}
```

**Flag:**
```bash
pwn.college{OKduHK2HtDP0eZRHP1mbZtSrVk0.QXlQTN0wyN2MDM1EzW}
```

### Challenge: Position Thy Self

**Task:**
The goal of this challenge is to understand how the current working directory affects program execution and how to change directories correctly before running a program.


**Commands Used:**
```bash
ssh hacker@dojo.pwn.college
/challenge/run
cd /proc/133
/challenge/run
```

**Explanation:**

In Linux, each command runs from a specific directory location. Some challenges require being in the correct directory before a program can execute properly.

When /challenge/run was executed from the wrong directory, the program returned an error message indicating the required directory. The message explicitly stated that the current directory was incorrect and mentioned /proc/133 as the correct location.

 Using this , the cd command was used to navigate to the /proc/133 directory which correctly display the flag. 

**Output:**
```bash
Incorrect...
You are not currently in the /proc/133 directory.
Please use the 'cd' utility to change directory appropriately.


Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
pwn.college{40kMXcpzcnFXKm7dFjUPsxt26Bn.QX2QTN0wyN2MDM1EzW}

```

**Flag:**
```bash
pwn.college{40kMXcpzcnFXKm7dFjUPsxt26Bn.QX2QTN0wyN2MDM1EzW}

```

### Challenge: Position Elsewhere

**Task:**
The objective of this challenge is to execute a program from specific directories as instructed, using absolute paths, in order to progress through multiple levels and obtain the flag.

**Commands Used:**
```bash
ssh hacker@dojo.pwn.college

/challenge/run
cd /var/log
/challenge/run

cd /var/lib/apt/lists
/challenge/run

cd /
/challenge/run

cd /home
/challenge/run

cd /etc
/challenge/run

/challenge/run
```

**Explanation:**

This challenge demonstrates that a program’s execution can depend on the current working directory. Running /challenge/run initially resulted in an error message specifying the required directory.

The cd command was used to move to the directory mentioned by the program. Once in the correct location, the program was executed again using its absolute path. This process was repeated multiple times, with each level requiring a different directory before execution was accepted.


**Output:**
```bash
Starting level 1.
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Moving on to level 2
Please use the `cd` utility to change directory to /var/lib/apt/lists
till (level5)

Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
pwn.college{UcijdgGeoWcdhp8xZHjDSx5ZakH.QX3QTN0wyN2MDM1EzW}

```

**Flag:**
```bash
pwn.college{UcijdgGeoWcdhp8xZHjDSx5ZakH.QX3QTN0wyN2MDM1EzW}

```
## Challenge: Implicit Relative Paths, from /

**Task:**
The objective of this challenge was to run the challenge/run program using a relative path while being in the root (/) directory. Absolute paths were not allowed for this level.

**Commands Used:**
```bash
ssh hacker@dojo.pwn.college
/challenge/run
cd /
challenge/run
```
**Explanation:**

The challenge required executing the program using a relative path, which means the path must not start with /.
Initially, /challenge/run was used, but this failed because it is an absolute path, even though the directory was correct.

The prompt then required being in the root directory, so cd / was used to move there. Finally, running challenge/run worked because:
* It is a relative path
* From /, it correctly resolves to /challenge/run

**Output:**
```bash
Correct!!!
challenge/run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{gG4HWnIunAs07eNbu078hTDOcyE.QX5QTN0wyN2MDM1EzW}
```

**Flag:**
```bash
pwn.college{gG4HWnIunAs07eNbu078hTDOcyE.QX5QTN0wyN2MDM1EzW}

```

## Challenge: Explicit Relative Paths, from /

**Task:**
This challenge demonstrates how explicit relative paths work in Linux using . (current directory) and how they differ from absolute paths.

**Commands Used:**
```bash
ssh hacker@dojo.pwn.college
cd /
./challenge/run
```
**Explanation:**
The challenge required executing the program using a relative path, not an absolute one,the current working directory was changed to the root directory (/).Instead of using /challenge/run (absolute path), the program was executed as ./challenge/run.
Here, . explicitly refers to the current directory (/), making ./challenge/run a valid explicit relative path.

**Output:**
```bash
Correct!!!
./challenge/run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{Q_FNgYbPGhOD5RF4TzwUHaBOgFP.QXwUTN0wyN2MDM1EzW}
```

**Flag:**
```bash
pwn.college{Q_FNgYbPGh0D5RF4TzwUHaB0gFP.QXwUTN0wyN2MDM1EzW}

```


## Challenge: Implicit Relative Path

**Task:**
This challenge focuses on understanding how Linux uses implicit relative paths and how command execution works when the current directory is already set correctly.

**Commands Used:**
```bash
ssh hacker@dojo.pwn.college
cd /challenge
./run

```
**Explanation:**
In this level, the goal was to run the run program from inside the /challenge directory.
Linux does not automatically execute programs from the current directory unless explicitly told to do so.
The program was executed using ./run.Attempts like run alone fail because Linux avoids searching the current directory by default for security reasons.
Here:
* .refers to the current directory (/challenge)
* ./run explicitly tells Linux to execute the run file located in the current directory


**Output:**
```bash
Correct!!!
./run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{4CJtlowpWIpFIKA2eBpmCLs_nkT.QXwUTN0wyN2MDM1EzW}

```

**Flag:**
```bash
pwn.college{4CJtlowpWIpFIKA2eBpmCLs_nkT.QXwUTN0wyN2MDM1EzW}

```

## Challenge: Home Sweet Home

**Task:**
This challenge focuses on how the ~ shorthand expands to the home directory, allowing absolute paths to be formed under strict constraints.

**Commands Used:**
```bash
ssh hacker@dojo.pwn.college
/challenge/run ~/f
```

**Explanation:**
In this challenge, the /challenge/run program copies the flag to a file whose path is provided as an argument. However, the argument had to meet three constraints:
* It must be an absolute path
* It must point inside the home directory (/home/hacker)
* Before expansion, the argument must be 3 characters or fewer

Using a full path like /home/hacker/file failed because it exceeded the character limit.
The solution was to use (~), which represents the home directory and is expanded by the shell after the length check.

By using ~/f:
* ~ expands to /home/hacker
* The full path becomes /home/hacker/f
* The argument length before expansion is exactly 3 characters


**Output:**
```bash
Writing the file to /home/hacker/f!
…and reading it back to you:
pwn.college{Ugnvi_-e4beg-K7ZMvmU0pgS6Hk.QXzMDO0wyN2MDM1EzW}

```

**Flag:**
```bash
pwn.college{Ugnvi_-e4beg-K7ZMvmU0pgS6Hk.QXzMDO0wyN2MDM1EzW}
```

---

