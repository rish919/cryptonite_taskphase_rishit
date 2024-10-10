# Redirecting output
## Code
```
hacker@piping~redirecting-output:~$ echo PWN > COLLEGE
Correct! You successfully redirected 'PWN' to the file 'COLLEGE'! Here is your
flag:
pwn.college{Q7gYbvcGOZkoAY1gEiNnr2QcqpK.dRjN1QDLyQzN0czW}
```
## Approach
The given file name was COLLEGE where the word PWN needs to be inputted. This is done by redirecting stdout of PWN to the file using the > character.<br>
This returned the flag **pwn.college{Q7gYbvcGOZkoAY1gEiNnr2QcqpK.dRjN1QDLyQzN0czW}**
## Learning
Learnt input redirection using > character.
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
Checked for files in challenge and home directory.Used the > character for input redirection from file /challenge/run to myflag.Used cat command to read the myflag file.<br>
This returned the flag **pwn.college{4-yjjV9sdQHICGv5GOht_WKaEB1.dVjN1QDLyQzN0czW}**
## Learning
Learnt input redirection from file path to files using > character.

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
Checked for files in challenge and home directory. Used the > character for input redirection from file /challenge/run to the-flag. Used cat command to read the file, which displayed only the second part. This indicated that the second part was overwritten on the existing first. Next, used the >> character for appending to the file the-flag from /challenge/run. The cat command to the-flag now showed both parts of the flag.
.<br>
This returned the flag **pwn.college{8iM1AjOX0Od3HhcENe-ZFxFP69Q.ddDM5QDLyQzN0czW}**
## Learning
Learnt to use the >> character for appending to files in Linux.

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
Checked for files in challenge and home directory. Used the > character for input redirection from file /challenge/run to myflag. Use 2> command to redirect the standard error to instructions. Used cat instructions to read the feedback from instructions and cat myflag to read the flag.<br>
This returned the flag **pwn.college{gAqYH63kHuj43SjZWSweCr_6ugH.ddjN1QDLyQzN0czW}**
## Learning
When we redirect process communication, we do it by FD number, though some FD numbers are implicit. For example, a > without a number implies 1>, which redirects FD 1 (Standard Output). 2> redirects the standard error.

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
Redirected the word COLLEGE to PWN by using the echo COLLEGE > PWN command. Redirected the input to /challenge/run by using the command /challenge/run < PWN, having the < character.<br>
This returned the flag **pwn.college{o5pKfUJo16JE5ESnZxG3oX1IUc8.dBzN1QDLyQzN0czW}**
## Learning
We can redirect input to programs. This is done using < character.

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
Redirected the output of /challenge/run to /tmp/data.txt. After displaying the feedback and success of all execution requirements, grepped for pwn.college in the /tmp/data.txt file using the command grep pwn.college /tmp/data.txt.<br>
This returned the flag **pwn.college{k39V1-a-_67fDvy0f-BXkifmvNx.dhTM4QDLyQzN0czW}**
## Learning
Learnt how to run commands, how to redirect their output (e.g., >), and how to search through the resulting file (e.g., grep) together.

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
Using the pipe operator grep for pwn.college in /challenge/run directly without creating a new file. This is done using the command /challenge/run | grep pwn.college.<br>
This returned the flag **pwn.college{UgcrtNfBhZEjlu-HNtwxpVerGJ_.dlTM4QDLyQzN0czW}**
## Learning
Standard output from the command to the left of the pipe will be connected to (piped into) the standard input of the command to the right of the pipe.

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
Normally, 2> is used to redirect standard error (file descriptor 2) to a file, but this time we need to redirect stderr to standard output. This can be done using 2>&1, which combines both stderr and stdout. After combining stderr and stdout, we pipe this combined output to grep to filter and find specific patterns, which in this case is pwn.college. This the command stands as /challenge/run 2>&1 | grep pwn.college.<br>
This returned the flag **pwn.college{YwURPd-WjrAfhfzMxFvaBrd2vg_.dVDM5QDLyQzN0czW}**
## Learning
>& operator redirects a file descriptor to another file descriptor. This means that we can have a two-step process to grep through errors: first, we redirect standard error to standard output (2>& 1) and then pipe the now-combined stderr and stdout as normal (|).

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
Run the /challenge/pwn | /challenge/college to pipe the two programs directly, but the input to college did not contain the secret code. Then used 'tee' to 
duplicate data flowing into the pipes to college by running tee college in the middle. Then run cat college to access the secret argument to /challenge/pwn. After getting the argument as wSlxdv9R, run the desired command challenge/pwn --secret wSlxdv9R | /challenge/college. <br>
This returned the flag **pwn.college{wSlxdv9R1yMFyc9yPpeG8W26zBF.dFjM5QDLyQzN0czW}**
## Learning
Learnt to use the tee command, which duplicates data flowing through your pipes to any number of files provided on the command line.

# Writing to multiple programs
## Code
```
hacker@piping~writing-to-multiple-programs:~$ /challenge/hack | tee >(/challenge/the) | (/challenge/planet)
Congratulations, you have duplicated data into the input of two programs! Here
is your flag:
pwn.college{kQtrDGZ9Obmcv3yEv3k247IfTVI.dBDO0UDLyQzN0czW}
```
## Approach
The given file is /challenge/hack. Duplicated the output to inputs of /challenge/the and /challenge/planet by using the tee command in thie middle.<br>
This returned the flag **pwn.college{kQtrDGZ9Obmcv3yEv3k247IfTVI.dBDO0UDLyQzN0czW}**
## Learning
Learnt to write to multiple programs, by duplicating to two commands using tee command.

# Split piping stderr and stdout
## Code
```
hacker@piping~split-piping-stderr-and-stdout:~$ /challenge/hack | /challenge/planet 2> >(/challenge/the)
You must redirect my standard error into '/challenge/the'!
You are redirecting standard error *of /challenge/planet*! Instead, you must
redirect standard error of 'hack'. This must be done *before* any |. The right
side of the pipe is a different command, with its own redirection, than the
left side!
Are you sure you're properly redirecting /challenge/hack's standard error into
'/challenge/the'?
hacker@piping~split-piping-stderr-and-stdout:~$ /challenge/hack 2> >( /challenge/the ) | /challenge/planet
Congratulations, you have learned a redirection technique that even experts
struggle with! Here is your flag:
pwn.college{I9vbEMeaJCgxMUuxvvvRgkWyCtT.dFDNwYDLyQzN0czW}
```
## Approach
Tried redirecting output from /challenge/hack to /challenge/planet and standard error of /challenge/planet to /challenge/the, but it showed an error as I was redirecting standard error of /challenge/planet instead of /challenge/hack. Run the command /challenge/hack 2> >( /challenge/the ) | /challenge/planet which correctly ensures the redirection order. Here, stderr is redirected to /challenge/the before the pipe, and stdout is sent to /challenge/planet via the pipe.<br>
This returned the flag **pwn.college{I9vbEMeaJCgxMUuxvvvRgkWyCtT.dFDNwYDLyQzN0czW}**
## Learning
Used combined knowledge of >(), 2>, and | and learnt to use them together for redirection.
