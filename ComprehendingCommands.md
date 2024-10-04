# cat: not the pet, but the command
## Code
```
hacker@commands~cat-not-the-pet-but-the-command:~$ cat flag
pwn.college{4i2t2u-SCfTkBZVHwF9MtGrFkMw.dFzN1QDLyQzN0czW}
```
## Approach
The given file name was flag and the flag was copied into this file. To access this, read the file with the cat flag command in the home directory.<br>
This returned the flag **pwn.college{4i2t2u-SCfTkBZVHwF9MtGrFkMw.dFzN1QDLyQzN0czW}**
## Learning
Learnt to use the cat command to read a file in Linux.
# catting absolute paths
## Code
```
hacker@commands~catting-absolute-paths:~$ cat /flag
pwn.college{optiyLOfxCrNTtF0pEYgRq9CZAR.dlTM5QDLyQzN0czW}
```
## Approach
The given file name was flag and the flag was copied into this file. To access this, read the file with the cat /flag command with cat's argument being an absolute path.<br>
This returned the flag **pwn.college{optiyLOfxCrNTtF0pEYgRq9CZAR.dlTM5QDLyQzN0czW}**
## Learning
Learnt to use the cat command with absolute paths as arguments to read a file in Linux.
# catting absolute paths
## Code
```
You cannot use the 'cd' command in this level, and must retrieve the flag by
absolute path. Plus, I hid the flag in a different directory! You can find it
in the file /usr/aarch64-linux-gnu/include/flag. Go cat it out **without**
cding into that directory!
hacker@commands~more-catting-practice:~$ cat /usr/aarch64-linux-gnu/include/flag
pwn.college{sF5V6-df7GGxHqBESwgWo3DWgMq.dBjM5QDLyQzN0czW}
```
## Approach
The given file name was flag and the flag was copied into this file. The absolute path of the file was /usr/aarch64-linux-gnu/include/flag. To access the flag in the file, read the file with the cat /usr/aarch64-linux-gnu/include/flag command with cat's argument being the given absolute path.<br>
This returned the flag **pwn.college{sF5V6-df7GGxHqBESwgWo3DWgMq.dBjM5QDLyQzN0czW}**
## Learning
Learnt to use the cat command with absolute paths as arguments to read a file in Linux.
# grepping for a needle in a haystack
## Code
```
hacker@commands~grepping-for-a-needle-in-a-haystack:~$ grep pwn.college /challenge/data.txt
pwn.college{sr_hHIdq0SpxmVNx05sfc0ItGDo.ddTM4QDLyQzN0czW}
```
## Approach
The given file name was /challenge/data.txt where the flag was contained in a single line of the hundred thousand lines of the files. To access this, we grepped the line starting with pwn.college to access the flag that also always starts with pwn.college.<br>
This returned the flag **pwn.college{sr_hHIdq0SpxmVNx05sfc0ItGDo.ddTM4QDLyQzN0czW}**
## Learning
Learnt to use the grep command to read some portion of a file in Linux as strings.

