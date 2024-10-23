# Chaining with Semicolons
## Code
```
hacker@chaining~chaining-with-semicolons:~$ /challenge/pwn; /challenge/college
Yes! You chained /challenge/pwn and /challenge/college! Here is your flag:
pwn.college{EOaT5DG9-Osje7y0JdiIKzb8bok.dVTN4QDLyQzN0czW}
```
## Approach
.<br>
This returned the flag **pwn.college{EOaT5DG9-Osje7y0JdiIKzb8bok.dVTN4QDLyQzN0czW}**
## Learning

# Your First Shell Script
## Code
```
hacker@chaining~your-first-shell-script:~$ touch x.sh
hacker@chaining~your-first-shell-script:~$ echo /challenge/pwn > x.sh
hacker@chaining~your-first-shell-script:~$ echo /challenge/college >> x.sh
hacker@chaining~your-first-shell-script:~$ bash x.sh
Great job, you've written your first shell script! Here is the flag:
pwn.college{QXeAX3zHd12KpFlMzvjtHGlxPkb.dFzN4QDLyQzN0czW}
```
## Approach
.<br>
This returned the flag **pwn.college{QXeAX3zHd12KpFlMzvjtHGlxPkb.dFzN4QDLyQzN0czW}**
## Learning

# Redirecting Script Output
## Code
```
hacker@chaining~redirecting-script-output:~$ touch x.sh
hacker@chaining~redirecting-script-output:~$ echo /challenge/pwn > x.sh
hacker@chaining~redirecting-script-output:~$ echo /challenge/college >> x.sh
hacker@chaining~redirecting-script-output:~$ bash x.sh
It looks like you are not piping this script out to /challenge/solve! Remember
to pipe the output of your script into /challenge/solve using '|'.
hacker@chaining~redirecting-script-output:~$ bash x.sh | /challenge/solve
Correct! Here is your flag:
pwn.college{w-iivpshNqTiDAzsIPuTLzFhNbu.dhTM5QDLyQzN0czW}
```
## Approach
.<br>
This returned the flag **pwn.college{w-iivpshNqTiDAzsIPuTLzFhNbu.dhTM5QDLyQzN0czW}**
## Learning

# Executable Shell Scripts
## Code
```
hacker@chaining~executable-shell-scripts:~$ touch x.sh
hacker@chaining~executable-shell-scripts:~$ echo /challenge/solve > x.sh
hacker@chaining~executable-shell-scripts:~$ ./x.sh
ssh-entrypoint: ./x.sh: Permission denied
hacker@chaining~executable-shell-scripts:~$ chmod a=rwx x.sh
hacker@chaining~executable-shell-scripts:~$ ls -l x.sh
-rwxrwxrwx 1 hacker hacker 17 Oct 23 13:16 x.sh
hacker@chaining~executable-shell-scripts:~$ ./x.sh
Congratulations on your shell script execution! Your flag:
pwn.college{wMQjr3iGkxfS-asbH87oQ3AP5ml.dRzNyUDLyQzN0czW}
```
## Approach
.<br>
This returned the flag **pwn.college{wMQjr3iGkxfS-asbH87oQ3AP5ml.dRzNyUDLyQzN0czW}**
## Learning
