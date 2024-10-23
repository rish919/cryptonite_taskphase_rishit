# Becoming root with su
## Code
```
hacker@users~becoming-root-with-su:~$ ls -l /usr/bin/su
-rwxr-xr-x 1 root root 67816 Apr  9  2024 /usr/bin/su
hacker@users~becoming-root-with-su:~$ su
Password:
root@users~becoming-root-with-su:/home/hacker# cat /flag
pwn.college{0_GtMXK63NYWkI5YS4y_3Jpp6Tf.dVTN0UDLyQzN0czW}
```
## Approach
.<br>
This returned the flag **pwn.college{0_GtMXK63NYWkI5YS4y_3Jpp6Tf.dVTN0UDLyQzN0czW}**
## Learning

# Other users with su
## Code
```
-rwxr-xr-x 1 root root 67816 Apr  9  2024 /usr/bin/su
hacker@users~other-users-with-su:~$ su zardus
Password:
zardus@users~other-users-with-su:/home/hacker$ /challenge/run
Congratulations, you have become Zardus! Here is your flag:
pwn.college{AInroylhly2fgKTLVOhIhwM2i3q.dZTN0UDLyQzN0czW}
```
## Approach
.<br>
This returned the flag **pwn.college{AInroylhly2fgKTLVOhIhwM2i3q.dZTN0UDLyQzN0czW}**
## Learning

# Cracking passwords
## Code
```
hacker@users~cracking-passwords:~$ cd /challenge
hacker@users~cracking-passwords:/challenge$ ls -a
.  ..  .catflag  DESCRIPTION.md  bin  run  shadow-leak
hacker@users~cracking-passwords:/challenge$ john ./shadow-leak
Loaded 1 password hash (crypt, generic crypt(3) [?/64])
Press 'q' or Ctrl-C to abort, almost any other key for status
0g 0:00:00:07 66% 1/3 0g/s 230.8p/s 230.8c/s 230.8C/s z99999F..Zardus99999E
0g 0:00:00:18 0% 2/3 0g/s 240.4p/s 240.4c/s 240.4C/s grumpy..keeper
0g 0:00:00:20 1% 2/3 0g/s 245.2p/s 245.2c/s 245.2C/s pretty..celtic
0g 0:00:00:22 1% 2/3 0g/s 249.2p/s 249.2c/s 249.2C/s 10sne1..nermal
aardvark         (zardus)
1g 0:00:00:23 100% 2/3 0.04253g/s 247.6p/s 247.6c/s 247.6C/s Johnson..buzz
Use the "--show" option to display all of the cracked passwords reliably
Session completed
hacker@users~cracking-passwords:/challenge$ su zardus
Password:
zardus@users~cracking-passwords:/challenge$ /challenge/run
Congratulations, you have become Zardus! Here is your flag:
pwn.college{wURELLVgGyRnei9T2fU0ejrgJ8S.ddTN0UDLyQzN0czW}
```
## Approach
.<br>
This returned the flag **pwn.college{wURELLVgGyRnei9T2fU0ejrgJ8S.ddTN0UDLyQzN0czW}**
## Learning

# Using sudo
## Code
```
hacker@users~using-sudo:~$ cat /flag
cat: /flag: Permission denied
hacker@users~using-sudo:~$ sudo cat /flag
pwn.college{gmNzIwBaR8H5ibg85nStWfDwq8A.dhTN0UDLyQzN0czW}
```
## Approach
.<br>
This returned the flag **pwn.college{gmNzIwBaR8H5ibg85nStWfDwq8A.dhTN0UDLyQzN0czW}**
## Learning
