# Redirecting output
## Code
```
hacker@piping~redirecting-output:~$ echo PWN > COLLEGE
Correct! You successfully redirected 'PWN' to the file 'COLLEGE'! Here is your
flag:
pwn.college{Q7gYbvcGOZkoAY1gEiNnr2QcqpK.dRjN1QDLyQzN0czW}
```
## Approach
.<br>
This returned the flag **pwn.college{Q7gYbvcGOZkoAY1gEiNnr2QcqpK.dRjN1QDLyQzN0czW}**
## Learning

# Redirecting more output
## Code
```
hacker@piping~redirecting-more-output:~$ ls /challenge
DESCRIPTION.md  chio.py  run
hacker@piping~redirecting-more-output:~$ ls
COLLEGE  Desktop  myflag  not-the-flag  r
hacker@piping~redirecting-more-output:~$ /challenge/run > myflag
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : myflag
[INFO] - the challenge will output a reward file if all the tests pass : /flag

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /flag file.

[TEST] You should have redirected my stdout to a file called myflag. Checking...

[PASS] The file at the other end of my stdout looks okay!
[PASS] Success! You have satisfied all execution requirements.
hacker@piping~redirecting-more-output:~$ cat myflag

[FLAG] Here is your flag:
[FLAG] pwn.college{4-yjjV9sdQHICGv5GOht_WKaEB1.dVjN1QDLyQzN0czW}
```
## Approach
.<br>
This returned the flag **pwn.college{4-yjjV9sdQHICGv5GOht_WKaEB1.dVjN1QDLyQzN0czW}**
## Learning

# Appending output
## Code
```
hacker@piping~appending-output:~$ ls /challenge
DESCRIPTION.md  chio.py  run
hacker@piping~appending-output:~$ ls /home/hacker
COLLEGE  Desktop  myflag  not-the-flag  r  the-flag
hacker@piping~appending-output:~$ /challenge/run > /home/hacker/the-flag
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : /home/hacker/the-flag

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] Good luck!

[TEST] You should have redirected my stdout to a file called /home/hacker/the-flag. Checking...

[HINT] File descriptors are inherited from the parent, unless the FD_CLOEXEC is set by the parent on the file descriptor.
[HINT] For security reasons, some programs, such as python, do this by default in certain cases. Be careful if you are
[HINT] creating and trying to pass in FDs in python.

[PASS] The file at the other end of my stdout looks okay!
[PASS] Success! You have satisfied all execution requirements.
I will write the flag in two parts to the file /home/hacker/the-flag! I'll do
the first write directly to the file, and the second write, I'll do to stdout
(if it's pointing at the file). If you redirect the output in append mode, the
second write will append to (rather than overwrite) the first write, and you'll
get the whole flag!
hacker@piping~appending-output:~$ cat the-flag
AjOX0Od3HhcENe-ZFxFP69Q.ddDM5QDLyQzN0czW}
                              ^
     that is the second half /|\
                              |

If you only see the second half above, you redirected in *truncate* mode (>)
rather than *append* mode (>>), and so the write of the second half to stdout
overwrote the initial write of the first half directly to the file. Try append
mode!
hacker@piping~appending-output:~$ /challenge/run >> /home/hacker/the-flag
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : /home/hacker/the-flag

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] Good luck!

[TEST] You should have redirected my stdout to a file called /home/hacker/the-flag. Checking...

[HINT] File descriptors are inherited from the parent, unless the FD_CLOEXEC is set by the parent on the file descriptor.
[HINT] For security reasons, some programs, such as python, do this by default in certain cases. Be careful if you are
[HINT] creating and trying to pass in FDs in python.

[PASS] The file at the other end of my stdout looks okay!
[PASS] Success! You have satisfied all execution requirements.
I will write the flag in two parts to the file /home/hacker/the-flag! I'll do
the first write directly to the file, and the second write, I'll do to stdout
(if it's pointing at the file). If you redirect the output in append mode, the
second write will append to (rather than overwrite) the first write, and you'll
get the whole flag!
hacker@piping~appending-output:~$ cat the-flag
 |
\|/ This is the first half:
 v
pwn.college{8iM1AjOX0Od3HhcENe-ZFxFP69Q.ddDM5QDLyQzN0czW}
                              ^
     that is the second half /|\
                              |

If you only see the second half above, you redirected in *truncate* mode (>)
rather than *append* mode (>>), and so the write of the second half to stdout
overwrote the initial write of the first half directly to the file. Try append
mode!
```
## Approach
.<br>
This returned the flag **pwn.college{8iM1AjOX0Od3HhcENe-ZFxFP69Q.ddDM5QDLyQzN0czW}**
## Learning

# Redirecting errors
## Code
```
hacker@piping~redirecting-errors:~$ ls /challenge
DESCRIPTION.md  chio.py  run
hacker@piping~redirecting-errors:~$ ls
COLLEGE  Desktop  myflag  not-the-flag  r  the-flag
hacker@piping~redirecting-errors:~$ /challenge/run > myflag 2> instructions
hacker@piping~redirecting-errors:~$ cat instructions
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : myflag
[INFO] - the challenge will check that error output is redirected to a specific file path : instructions
[INFO] - the challenge will output a reward file if all the tests pass : /flag

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /flag file.

[TEST] You should have redirected my stdout to a file called myflag. Checking...

[PASS] The file at the other end of my stdout looks okay!

[TEST] You should have redirected my stderr to instructions. Checking...

[PASS] The file at the other end of my stderr looks okay!
[PASS] Success! You have satisfied all execution requirements.
hacker@piping~redirecting-errors:~$ cat myflag

[FLAG] Here is your flag:
[FLAG] pwn.college{gAqYH63kHuj43SjZWSweCr_6ugH.ddjN1QDLyQzN0czW}
```
## Approach
.<br>
This returned the flag **pwn.college{gAqYH63kHuj43SjZWSweCr_6ugH.ddjN1QDLyQzN0czW}**
## Learning

# Redirecting input
## Code
```
hacker@piping~redirecting-input:~$ echo COLLEGE > PWN
hacker@piping~redirecting-input:~$ /challenge/run < PWN
Reading from standard input...
Correct! You have redirected the PWN file into my standard input, and I read
the value 'COLLEGE' out of it!
Here is your flag:
pwn.college{o5pKfUJo16JE5ESnZxG3oX1IUc8.dBzN1QDLyQzN0czW}
```
## Approach
.<br>
This returned the flag **pwn.college{o5pKfUJo16JE5ESnZxG3oX1IUc8.dBzN1QDLyQzN0czW}**
## Learning

# Grepping stored results
## Code
```
hacker@piping~grepping-stored-results:~$ /challenge/run > /tmp/data.txt
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : /tmp/data.txt
[INFO] - the challenge will output a reward file if all the tests pass : /challenge/.data.txt

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /challenge/.data.txt file.

[TEST] You should have redirected my stdout to a file called /tmp/data.txt. Checking...

[HINT] File descriptors are inherited from the parent, unless the FD_CLOEXEC is set by the parent on the file descriptor.
[HINT] For security reasons, some programs, such as python, do this by default in certain cases. Be careful if you are
[HINT] creating and trying to pass in FDs in python.

[PASS] The file at the other end of my stdout looks okay!
[PASS] Success! You have satisfied all execution requirements.
hacker@piping~grepping-stored-results:~$ grep pwn.college /tmp/data.txt
pwn.college{k39V1-a-_67fDvy0f-BXkifmvNx.dhTM4QDLyQzN0czW}
```
## Approach
.<br>
This returned the flag **pwn.college{k39V1-a-_67fDvy0f-BXkifmvNx.dhTM4QDLyQzN0czW}**
## Learning

# Grepping live output
## Code
```
hacker@piping~grepping-live-output:~$ /challenge/run | grep pwn.college
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge checks for a specific process at the other end of stdout : grep
[INFO] - the challenge will output a reward file if all the tests pass : /challenge/.data.txt

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /challenge/.data.txt file.

[TEST] You should have redirected my stdout to another process. Checking...
[TEST] Performing checks on that process!

[INFO] The process' executable is /nix/store/xpq4yhadyhazkcsggmqd7rsgvxb3kjy4-gnugrep-3.11/bin/grep.
[INFO] This might be different than expected because of symbolic links (for example, from /usr/bin/python to /usr/bin/python3 to /usr/bin/python3.8).
[INFO] To pass the checks, the executable must be grep.

[PASS] You have passed the checks on the process on the other end of my stdout!
[PASS] Success! You have satisfied all execution requirements.
pwn.college{UgcrtNfBhZEjlu-HNtwxpVerGJ_.dlTM4QDLyQzN0czW}
```
## Approach
.<br>
This returned the flag **pwn.college{UgcrtNfBhZEjlu-HNtwxpVerGJ_.dlTM4QDLyQzN0czW}**
## Learning

# Grepping errors
## Code
```
hacker@piping~grepping-errors:~$ /challenge/run 2>&1 | grep pwn.college
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge checks for a specific process at the other end of stderr : grep
[INFO] - the challenge will output a reward file if all the tests pass : /challenge/.data.txt

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /challenge/.data.txt file.

[TEST] You should have redirected my stderr to another process. Checking...
[TEST] Performing checks on that process!

[INFO] The process' executable is /nix/store/xpq4yhadyhazkcsggmqd7rsgvxb3kjy4-gnugrep-3.11/bin/grep.
[INFO] This might be different than expected because of symbolic links (for example, from /usr/bin/python to /usr/bin/python3 to /usr/bin/python3.8).
[INFO] To pass the checks, the executable must be grep.

[PASS] You have passed the checks on the process on the other end of my stderr!
[PASS] Success! You have satisfied all execution requirements.
pwn.college{YwURPd-WjrAfhfzMxFvaBrd2vg_.dVDM5QDLyQzN0czW}
```
## Approach
.<br>
This returned the flag **pwn.college{YwURPd-WjrAfhfzMxFvaBrd2vg_.dVDM5QDLyQzN0czW}**
## Learning

# Duplicating piped data with tee
## Code
```
hacker@piping~duplicating-piped-data-with-tee:~$ /challenge/pwn | /challenge/college
Processing...
The input to 'college' does not contain the correct secret code! This code
should be provided by the 'pwn' command. HINT: use 'tee' to intercept the
output of 'pwn' and figure out what the code needs to be.
hacker@piping~duplicating-piped-data-with-tee:~$ ls /challenge
DESCRIPTION.md  bin  chio.py  college  pwn
hacker@piping~duplicating-piped-data-with-tee:~$ /challenge/pwn | tee college | /challenge/college
Processing...
The input to 'college' does not contain the correct secret code! This code
should be provided by the 'pwn' command. HINT: use 'tee' to intercept the
output of 'pwn' and figure out what the code needs to be.
hacker@piping~duplicating-piped-data-with-tee:~$ cat college
Usage: /challenge/pwn --secret [SECRET_ARG]

SECRET_ARG should be "wSlxdv9R"
hacker@piping~duplicating-piped-data-with-tee:~$ /challenge/pwn --secret wSlxdv9R | /challenge/college
Processing...
Correct! Passing secret value to /challenge/college...
Great job! Here is your flag:
pwn.college{wSlxdv9R1yMFyc9yPpeG8W26zBF.dFjM5QDLyQzN0czW}
```
## Approach
.<br>
This returned the flag **pwn.college{wSlxdv9R1yMFyc9yPpeG8W26zBF.dFjM5QDLyQzN0czW}**
## Learning

# Writing to multiple programs
## Code
```

```
## Approach
.<br>
This returned the flag ****
## Learning

# Split piping stderr and stdout
## Code
```

```
## Approach
.<br>
This returned the flag ****
## Learning
