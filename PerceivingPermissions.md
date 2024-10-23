# Changing File Ownership
## Code
```
hacker@permissions~changing-file-ownership:~$ ls -l /flag
-r-------- 1 root root 58 Oct 23 10:00 /flag
hacker@permissions~changing-file-ownership:~$ chown hacker /flag
hacker@permissions~changing-file-ownership:~$ cat /flag
pwn.college{Yd6WCrV9VRecAhK-TyKIk-J6KLI.dFTM2QDLyQzN0czW}
```
## Approach
.<br>
This returned the flag **pwn.college{Yd6WCrV9VRecAhK-TyKIk-J6KLI.dFTM2QDLyQzN0czW}**
## Learning

# Groups and Files
## Code
```
hacker@permissions~groups-and-files:~$ ls -l /flag
-r--r----- 1 root root 58 Oct 23 10:05 /flag
hacker@permissions~groups-and-files:~$ chgrp hacker /flag
hacker@permissions~groups-and-files:~$ cat /flag
pwn.college{IRTjmHpoDtgZnXNzRvWp-MJ-PWg.dFzNyUDLyQzN0czW}
```
## Approach
.<br>
This returned the flag **pwn.college{IRTjmHpoDtgZnXNzRvWp-MJ-PWg.dFzNyUDLyQzN0czW}**
## Learning

# Fun With Group Names
## Code
```
hacker@permissions~fun-with-groups-names:~$ id
uid=1000(hacker) gid=1000(grp13446) groups=1000(grp13446)
hacker@permissions~fun-with-groups-names:~$ ls -l /flag
-r--r----- 1 root root 58 Oct 23 10:13 /flag
hacker@permissions~fun-with-groups-names:~$ chgrp grp13446 /flag
hacker@permissions~fun-with-groups-names:~$ cat /flag
pwn.college{Mtm4CqZz1fP4k-Tt5X-K4F-Drt4.dJzNyUDLyQzN0czW}
```
## Approach
.<br>
This returned the flag **pwn.college{Mtm4CqZz1fP4k-Tt5X-K4F-Drt4.dJzNyUDLyQzN0czW}**
## Learning

# Changing Permissions
## Code
```
hacker@permissions~changing-permissions:~$ ls -l /flag
-r-------- 1 root root 58 Oct 23 10:29 /flag
hacker@permissions~changing-permissions:~$ chmod o+r /flag
hacker@permissions~changing-permissions:~$ ls -l /flag
-r-----r-- 1 root root 58 Oct 23 10:29 /flag
hacker@permissions~changing-permissions:~$ cat /flag
pwn.college{Ud30_nGJprg4QvmPbi5Xv5OaHpO.dNzNyUDLyQzN0czW}
```
## Approach
.<br>
This returned the flag **pwn.college{Ud30_nGJprg4QvmPbi5Xv5OaHpO.dNzNyUDLyQzN0czW}**
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

# 
## Code
```

```
## Approach
.<br>
This returned the flag ****
## Learning

