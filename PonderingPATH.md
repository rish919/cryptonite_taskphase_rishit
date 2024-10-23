# The PATH Variable
## Code
```
hacker@path~the-path-variable:~$ PATH=""
hacker@path~the-path-variable:~$ /challenge/run
Trying to remove /flag...
/challenge/run: line 4: rm: No such file or directory
The flag is still there! I might as well give it to you!
pwn.college{oVdqDua_WTLZNsW8JHc7pKqakEl.dZzNwUDLyQzN0czW}
```
## Approach
.<br>
This returned the flag **pwn.college{oVdqDua_WTLZNsW8JHc7pKqakEl.dZzNwUDLyQzN0czW}**
## Learning

# Setting PATH
## Code
```
hacker@path~setting-path:~$ PATH=/challenge/more_commands/
hacker@path~setting-path:~$ /challenge/run
Invoking 'win'....
Congratulations! You properly set the flag and 'win' has launched!
pwn.college{ULdeZxbkms5EinqrLQkkfeI3Zpk.dVzNyUDLyQzN0czW}
```
## Approach
.<br>
This returned the flag **pwn.college{ULdeZxbkms5EinqrLQkkfeI3Zpk.dVzNyUDLyQzN0czW}**
## Learning

# Adding Commands
## Code
```
hacker@path~adding-commands:~$ echo "cat /flag" > win
hacker@path~adding-commands:~$ chmod a=rwx win
hacker@path~adding-commands:~$ export PATH=$(pwd):$PATH
hacker@path~adding-commands:~$ /challenge/run
Invoking 'win'....
pwn.college{AoY1EHS2i3iSMsbkZF6CJN1T-4o.dZzNyUDLyQzN0czW}
```
## Approach
.<br>
This returned the flag **pwn.college{AoY1EHS2i3iSMsbkZF6CJN1T-4o.dZzNyUDLyQzN0czW}**
## Learning

# Hijacking Commands
## Code
```

```
## Approach
.<br>
This returned the flag ****
## Learning
