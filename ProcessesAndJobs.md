# Listing Processes
## Code
```
hacker@processes~listing-processes:~$ ps aux
USER         PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
root           1  0.6  0.0   1056   640 ?        Ss   06:20   0:00 /sbin/docker-init -- /nix/var/nix/profiles/default/bin/dojo-init /run/dojo/bin/sleep 6h
root           7  0.1  0.0   5052  2560 ?        S    06:20   0:00 /run/dojo/bin/sleep 6h
root          68  0.0  0.0   4132  2560 ?        S    06:20   0:00 /challenge/21326-run-21726
root          72  0.0  0.0   2744  1280 ?        S    06:20   0:00 sleep 6h
hacker        73  0.8  0.0   5372  3840 pts/0    Ss   06:20   0:00 /run/dojo/bin/ssh-entrypoint
hacker        90  0.0  0.0   7868  3200 pts/0    R+   06:20   0:00 ps aux
hacker@processes~listing-processes:~$ /challenge/21326-run-21726
Yahaha, you found me! Here is your flag:
pwn.college{MWVnUyPcFswSgV4Pop-sWnXaFOj.dhzM4QDLyQzN0czW}
Now I will sleep for a while (so that you could find me with 'ps').
```
## Approach
.<br>
This returned the flag **pwn.college{MWVnUyPcFswSgV4Pop-sWnXaFOj.dhzM4QDLyQzN0czW}**
## Learning

# Killing Processes
## Code
```
hacker@processes~killing-processes:~$ ps -e | grep sleep
     74 ?        00:00:00 sleep
hacker@processes~killing-processes:~$ kill 74
hacker@processes~killing-processes:~$ /challenge/run
Great job! Here is your payment:
pwn.college{E2v_9hqFu1BwlGM-zIMjhZotZRp.dJDN4QDLyQzN0czW}
```
## Approach
.<br>
This returned the flag **pwn.college{E2v_9hqFu1BwlGM-zIMjhZotZRp.dJDN4QDLyQzN0czW}**
## Learning

# Interrupting Processes
## Code
```
hacker@processes~interrupting-processes:~$ /challenge/run
I could give you the flag... but I won't, until this process exits. Remember,
you can force me to exit with Ctrl-C. Try it now!
^C
Good job! You have used Ctrl-C to interrupt this process! Here is your flag:
pwn.college{MAIaDwRltyDHJrlpNcgdYH0laTe.dNDN4QDLyQzN0czW}
```
## Approach
.<br>
This returned the flag **pwn.college{MAIaDwRltyDHJrlpNcgdYH0laTe.dNDN4QDLyQzN0czW}**
## Learning

# Suspending Processes
## Code
```
hacker@processes~suspending-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running in
this terminal... Let's check!

UID          PID    PPID  C STIME TTY          TIME CMD
root          82      65  0 06:50 pts/0    00:00:00 bash /challenge/run
root          84      82  0 06:50 pts/0    00:00:00 ps -f

I don't see a second me!

To pass this level, you need to suspend me and launch me again! You can
background me with Ctrl-Z or, if you're not ready to do that for whatever
reason, just hit Enter and I'll exit!
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~suspending-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running in
this terminal... Let's check!

UID          PID    PPID  C STIME TTY          TIME CMD
root          82      65  0 06:50 pts/0    00:00:00 bash /challenge/run
root          89      65  0 06:50 pts/0    00:00:00 bash /challenge/run
root          91      89  0 06:50 pts/0    00:00:00 ps -f

Yay, I found another version of me! Here is the flag:
pwn.college{A3E79Hv6KLMIWAoUo30MnXSZ6GQ.dVDN4QDLyQzN0czW}
```
## Approach
.<br>
This returned the flag **pwn.college{A3E79Hv6KLMIWAoUo30MnXSZ6GQ.dVDN4QDLyQzN0czW}**
## Learning

# Resuming Processes
## Code
```
hacker@processes~resuming-processes:~$ /challenge/run
Let's practice resuming processes! Suspend me with Ctrl-Z, then resume me with
the 'fg' command! Or just press Enter to quit me!
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~resuming-processes:~$ fg
/challenge/run
I'm back! Here's your flag:
pwn.college{YHjN6IDe8Z_eKCX3OmFn2AMaGTp.dZDN4QDLyQzN0czW}
Don't forget to press Enter to quit me!

Goodbye!
```
## Approach
.<br>
This returned the flag **pwn.college{YHjN6IDe8Z_eKCX3OmFn2AMaGTp.dZDN4QDLyQzN0czW}**
## Learning

# Backgrounding Processes
## Code
```
hacker@processes~backgrounding-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running *and
not suspended* in this terminal... Let's check!

UID          PID STAT CMD
root          82 S+   bash /challenge/run
root          84 R+   ps -o user=UID,pid,stat,cmd

I don't see a second me!

To pass this level, you need to suspend me, resume the suspended process in the
background, and then launch a new version of me! You can background me with
Ctrl-Z (and resume me in the background with 'bg') or, if you're not ready to
do that for whatever reason, just hit Enter and I'll exit!
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~backgrounding-processes:~$ bg
[1]+ /challenge/run &



Yay, I'm now running the background! Because of that, this text will probably
overlap weirdly with the shell prompt. Don't panic; just hit Enter a few times
to scroll this text out.

hacker@processes~backgrounding-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running *and
not suspended* in this terminal... Let's check!

UID          PID STAT CMD
root          82 S    bash /challenge/run
root          92 S    sleep 6h
root          93 S+   bash /challenge/run
root          95 R+   ps -o user=UID,pid,stat,cmd

Yay, I found another version of me running in the background! Here is the flag:
pwn.college{oMlFp02zAucRmjhRQarvBzuW3i5.ddDN4QDLyQzN0czW}
```
## Approach
.<br>
This returned the flag **pwn.college{oMlFp02zAucRmjhRQarvBzuW3i5.ddDN4QDLyQzN0czW}**
## Learning

# 
## Code
```

```
## Approach
.<br>
This returned the flag ****
## Learning

# 
## Code
```

```
## Approach
.<br>
This returned the flag ****
## Learning

# 
## Code
```

```
## Approach
.<br>
This returned the flag ****
## Learning
