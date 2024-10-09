# Redirecting output
## 
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
## 
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
## 
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
## 
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
## 
```

```
## Approach
.<br>
This returned the flag ****
## Learning

# Grepping stored results
## 
```

```
## Approach
.<br>
This returned the flag ****
## Learning

# Grepping live output
## 
```

```
## Approach
.<br>
This returned the flag ****
## Learning

# Grepping errors
## 
```

```
## Approach
.<br>
This returned the flag ****
## Learning

# Duplicating piped data with tee
## 
```

```
## Approach
.<br>
This returned the flag ****
## Learning

# Writing to multiple programs
## 
```

```
## Approach
.<br>
This returned the flag ****
## Learning

# Split piping stderr and stdout
## 
```

```
## Approach
.<br>
This returned the flag ****
## Learning
