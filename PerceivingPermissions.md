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

# Executable Files
## Code
```
hacker@permissions~executable-files:~$ /challenge/run
ssh-entrypoint: /challenge/run: Permission denied
hacker@permissions~executable-files:~$ ls -l /challenge/run
-r--r--r-- 1 hacker hacker 32 Jul  4 06:37 /challenge/run
hacker@permissions~executable-files:~$ chmod u+x /challenge/run
hacker@permissions~executable-files:~$ ls -l /challenge/run
-r-xr--r-- 1 hacker hacker 32 Jul  4 06:37 /challenge/run
hacker@permissions~executable-files:~$ /challenge/run
Successful execution! Here is your flag:
pwn.college{syxYlyjlb4qoPoWv2QiANXOcFBC.dJTM2QDLyQzN0czW}
```
## Approach
.<br>
This returned the flag **pwn.college{syxYlyjlb4qoPoWv2QiANXOcFBC.dJTM2QDLyQzN0czW}**
## Learning

# Permission Tweaking Practice
## Code
```
hacker@permissions~permission-tweaking-practice:~$ /challenge/run
Round 0 (of 8)!

Current permissions of "/challenge/pwn": rw-r--r--
* the user does have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": rw-rwxrwx
* the user does have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
* the group does have write permissions
* the group does have execute permissions
* the world does have read permissions
* the world does have write permissions
* the world does have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod go+wx /challenge/pwn
You set the correct permissions!
Round 1 (of 8)!

Current permissions of "/challenge/pwn": rw-rwxrwx
* the user does have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
* the group does have write permissions
* the group does have execute permissions
* the world does have read permissions
* the world does have write permissions
* the world does have execute permissions

Needed permissions of "/challenge/pwn": r--rwxr--
* the user does have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
* the group does have write permissions
* the group does have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod uo-wx /challenge/pwn
You set the correct permissions!
Round 2 (of 8)!

Current permissions of "/challenge/pwn": r--rwxr--
* the user does have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
* the group does have write permissions
* the group does have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": r--------
* the user does have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod go-rwx /challenge/pwn
You set the correct permissions!
Round 3 (of 8)!

Current permissions of "/challenge/pwn": r--------
* the user does have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": r-x------
* the user does have read permissions
- the user doesn't have write permissions
* the user does have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod u+x /challenge/pwn
You set the correct permissions!
Round 4 (of 8)!

Current permissions of "/challenge/pwn": r-x------
* the user does have read permissions
- the user doesn't have write permissions
* the user does have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": r-x-----x
* the user does have read permissions
- the user doesn't have write permissions
* the user does have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
* the world does have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod o+x /challenge/pwn
You set the correct permissions!
Round 5 (of 8)!

Current permissions of "/challenge/pwn": r-x-----x
* the user does have read permissions
- the user doesn't have write permissions
* the user does have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
* the world does have execute permissions

Needed permissions of "/challenge/pwn": r-xrw-rwx
* the user does have read permissions
- the user doesn't have write permissions
* the user does have execute permissions
* the group does have read permissions
* the group does have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
* the world does have write permissions
* the world does have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod go+rw /challenge/pwn
You set the correct permissions!
Round 6 (of 8)!

Current permissions of "/challenge/pwn": r-xrw-rwx
* the user does have read permissions
- the user doesn't have write permissions
* the user does have execute permissions
* the group does have read permissions
* the group does have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
* the world does have write permissions
* the world does have execute permissions

Needed permissions of "/challenge/pwn": r-xrw-rw-
* the user does have read permissions
- the user doesn't have write permissions
* the user does have execute permissions
* the group does have read permissions
* the group does have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
* the world does have write permissions
- the world doesn't have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod o-x /challenge/pwn
You set the correct permissions!
Round 7 (of 8)!

Current permissions of "/challenge/pwn": r-xrw-rw-
* the user does have read permissions
- the user doesn't have write permissions
* the user does have execute permissions
* the group does have read permissions
* the group does have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
* the world does have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": rwxrwxrwx
* the user does have read permissions
* the user does have write permissions
* the user does have execute permissions
* the group does have read permissions
* the group does have write permissions
* the group does have execute permissions
* the world does have read permissions
* the world does have write permissions
* the world does have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod ugo+rwx /challenge/pwn
You set the correct permissions!
You've solved all 8 rounds! I have changed the ownership
of the /flag file so that you can 'chmod' it. You won't be able to read
it until you make it readable with chmod!

Current permissions of "/flag": ---------
- the user doesn't have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod u+r /flag
hacker@permissions~permission-tweaking-practice:~$ cat /flag
pwn.college{cugdhmWUVkjM8PQzLIJr322bHwp.dBTM2QDLyQzN0czW}
```
## Approach
.<br>
This returned the flag **pwn.college{cugdhmWUVkjM8PQzLIJr322bHwp.dBTM2QDLyQzN0czW}**
## Learning

# Permissions Setting Practice
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

