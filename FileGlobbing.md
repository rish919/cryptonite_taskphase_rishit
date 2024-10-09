# Matching with *
## Code
```
hacker@globbing~matching-with-:~$ cd /ch*
hacker@globbing~matching-with-:/challenge$ /challenge/run
You ran me with the working directory of /challenge! Here is your flag:
pwn.college{kYn_fpsTcvvO7vkzuFcAIKKEGH0.dFjM4QDLyQzN0czW}
```
## Approach
.<br>
This returned the flag **pwn.college{kYn_fpsTcvvO7vkzuFcAIKKEGH0.dFjM4QDLyQzN0czW}**
## Learning

# Matching with ?
## Code
```
hacker@globbing~matching-with-:~$ cd /?ha??enge
hacker@globbing~matching-with-:/challenge$ /challenge/run
You ran me with the working directory of /challenge! Here is your flag:
pwn.college{gg1xbkUU4FNn1QZfS99KOhEfTtn.dJjM4QDLyQzN0czW}
```
## Approach
.<br>
This returned the flag **pwn.college{gg1xbkUU4FNn1QZfS99KOhEfTtn.dJjM4QDLyQzN0czW}**
## Learning

# Matching with []
## Code
```
hacker@globbing~matching-with-:~$ ls /challenge/files
file_a  file_c  file_e  file_g  file_i  file_k  file_m  file_o  file_q  file_s  file_u  file_w  file_y
file_b  file_d  file_f  file_h  file_j  file_l  file_n  file_p  file_r  file_t  file_v  file_x  file_z
hacker@globbing~matching-with-:~$ cd /challenge/files
hacker@globbing~matching-with-:/challenge/files$ /challenge/run file_[bash]
You got it! Here is your flag!
pwn.college{UmpF3NAsAInHc6VT-PLNSCjl0dI.dNjM4QDLyQzN0czW}
```
## Approach
.<br>
This returned the flag **pwn.college{UmpF3NAsAInHc6VT-PLNSCjl0dI.dNjM4QDLyQzN0czW}**
## Learning

# Matching paths with []
## Code
```
hacker@globbing~matching-paths-with-:~$ ls /challenge/files
file_a  file_c  file_e  file_g  file_i  file_k  file_m  file_o  file_q  file_s  file_u  file_w  file_y
file_b  file_d  file_f  file_h  file_j  file_l  file_n  file_p  file_r  file_t  file_v  file_x  file_z
hacker@globbing~matching-paths-with-:~$ /challenge/run /challenge/files/file_[bash]
You got it! Here is your flag!
pwn.college{YA8A-Wh_v_j9kYNjLmOQwDCRDrT.dRjM4QDLyQzN0czW}
```
## Approach
.<br>
This returned the flag **pwn.college{YA8A-Wh_v_j9kYNjLmOQwDCRDrT.dRjM4QDLyQzN0czW}**
## Learning

# Mixing globs
## Code
```
hacker@globbing~mixing-globs:~$ ls /challenge/files
amazing      delightful   great       jovial    magical     pwning   splendid   victorious  youthful
beautiful    educational  happy       kind      nice        queenly  thrilling  wonderful   zesty
challenging  fantastic    incredible  laughing  optimistic  radiant  uplifting  xenial
hacker@globbing~mixing-globs:~$ cd /challenge/files
hacker@globbing~mixing-globs:/challenge/files$ /challenge/run [c*e*p*]
Error: your argument is too long! It must be 6 characters or less.
hacker@globbing~mixing-globs:/challenge/files$ /challenge/run [cep]
Your expansion did not expand to the requested files (challenging, educational,
pwning). Instead, it expanded to:
[cep]
hacker@globbing~mixing-globs:/challenge/files$ /challenge/run [cep]*
You got it! Here is your flag!
pwn.college{QFv7-sQ1vmBV_oKQUoVrFcVdwvT.dVjM4QDLyQzN0czW}
```
## Approach
.<br>
This returned the flag **pwn.college{QFv7-sQ1vmBV_oKQUoVrFcVdwvT.dVjM4QDLyQzN0czW}**
## Learning

# Exclusionary globbing
## Code
```
hacker@globbing~exclusionary-globbing:~$ ls /challenge/files
amazing      delightful   great       jovial    magical     pwning   splendid   victorious  youthful
beautiful    educational  happy       kind      nice        queenly  thrilling  wonderful   zesty
challenging  fantastic    incredible  laughing  optimistic  radiant  uplifting  xenial
hacker@globbing~exclusionary-globbing:~$ cd /challenge/files
hacker@globbing~exclusionary-globbing:/challenge/files$ /challenge/run [^pwn]*
You got it! Here is your flag!
pwn.college{wvssRP6xWiPawrlrZdG-TmN2A8y.dZjM4QDLyQzN0czW}
```
## Approach
.<br>
This returned the flag **pwn.college{wvssRP6xWiPawrlrZdG-TmN2A8y.dZjM4QDLyQzN0czW}**
## Learning

