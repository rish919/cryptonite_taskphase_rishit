# The Root
## Code
```
hacker@paths~the-root:~$ /pwn
BOOM!!!
Here is your flag:
pwn.college{cUpPdP8KNUbGRQBH3Cl0rTJZux1.dhzN5QDLyQzN0czW}
```
## Approach
As mentioned in the description, there was an added program right in /, called pwn, that will give us the flag. Invoked the program by providing its path on the command line, starting from /, as /pwn.<br>
This returned the flag **pwn.college{cUpPdP8KNUbGRQBH3Cl0rTJZux1.dhzN5QDLyQzN0czW}**
## Learning
The path that starts with the root directory, is referred to as an "absolute path". Learnt the usage of an absolute path.
# Program and absolute paths
## Code
```
hacker@paths~program-and-absolute-paths:~$ /challenge
ssh-entrypoint: /challenge: Is a directory
hacker@paths~program-and-absolute-paths:~$ /challenge/run
Correct!!!
/challenge/run is an absolute path! Here is your flag:
pwn.college{4e6xkOc52XI6A5-TiHsn2ehnOcT.dVDN1QDLyQzN0czW}
```
## Approach
As mentioned in the description, there was an added program in the challenge directory, called run, and getting this will give us the flag. Invoked the challenge directory first by providing its path on the command line, starting from /, as /challenge.
Then invoked the run program in the directory by executing /challenge/run.<br>
This returned the flag **pwn.college{4e6xkOc52XI6A5-TiHsn2ehnOcT.dVDN1QDLyQzN0czW}**
## Learning
Learnt to access programs by invoking their directories in absolute paths.
# Position thy self
## Code
```
hacker@paths~position-thy-self:~$ /challenge/run
Incorrect...
You are not currently in the /var/lib/apt/lists directory.
Please use the `cd` utility to change directory appropriately.
hacker@paths~position-thy-self:~$ cd /var/lib/apt/lists
hacker@paths~position-thy-self:/var/lib/apt/lists$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
pwn.college{sZNwngFH1FHbbIjdGLWJv4Rd6sh.dZDN1QDLyQzN0czW}
```
## Approach
Tried to run the program without any change in directory, right from the bash shell. It did not execute and mentioned the directory that was needed to be changed to. Changed to directory /var/lib/apt/lists using cd command and then finally executed the /challenge/run program from the specific path.<br>
This returned the flag **pwn.college{sZNwngFH1FHbbIjdGLWJv4Rd6sh.dZDN1QDLyQzN0czW}**
## Learning
Learnt to access programs by invoking their directories in absolute paths and from specific paths that can be changed from the current directory by using the cd command.
# Position elsewhere
## Code
```
hacker@paths~position-elsewhere:~$ /challenge/run
Incorrect...
You are not currently in the /proc/67 directory.
Please use the `cd` utility to change directory appropriately.
hacker@paths~position-elsewhere:~$ cd /proc/67
hacker@paths~position-elsewhere:/proc/67$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
pwn.college{Iwq0XkopJBXQEb3YNkVn6YttQvi.ddDN1QDLyQzN0czW}
```
## Approach
Tried to run the program without any change in directory, right from the bash shell. It did not execute and mentioned the directory that was needed to be changed to. Changed to directory /proc/67 using cd command and then finally executed the /challenge/run program from the specific path. <br>
This returned the flag **pwn.college{Iwq0XkopJBXQEb3YNkVn6YttQvi.ddDN1QDLyQzN0czW}**
## Learning
Learnt to access programs by invoking their directories in absolute paths and from specific paths that can be changed from the current directory by using the cd command.
# Position yet elsewhere
## Code
```
hacker@paths~position-yet-elsewhere:~$ /challenge/run
Incorrect...
You are not currently in the /usr/include directory.
Please use the `cd` utility to change directory appropriately.
hacker@paths~position-yet-elsewhere:~$ cd /usr/include
hacker@paths~position-yet-elsewhere:/usr/include$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
pwn.college{8seGhbh3CwETzPd7hkeK0RvK4RH.dhDN1QDLyQzN0czW}
```
## Approach
Tried to run the program without any change in directory, right from the bash shell. It did not execute and mentioned the directory that was needed to be changed to. Changed to directory /usr/include using cd command and then finally executed the /challenge/run program from the specific path.<br>
This returned the flag **pwn.college{8seGhbh3CwETzPd7hkeK0RvK4RH.dhDN1QDLyQzN0czW}**
## Learning
Learnt to access programs by invoking their directories in absolute paths and from specific paths that can be changed from the current directory by using the cd command.
# implicit relative paths, from /
## Code
```
hacker@paths~implicit-relative-paths-from-:~$ cd /
hacker@paths~implicit-relative-paths-from-:/$ challenge/run
Correct!!!
challenge/run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{IdYfgAGyOXSJEE7x9-cMK1otKmK.dlDN1QDLyQzN0czW}
```
## Approach
As mentioned in description, the current working directory is /. Changed the cwd to / by using cd command. Invoked the program from / by executing the relative path challenge/run.<br>
This returned the flag **pwn.college{IdYfgAGyOXSJEE7x9-cMK1otKmK.dlDN1QDLyQzN0czW}**
## Learning
Learnt to access programs by invoking their directories in relative paths and from specific paths that can be changed from the current directory by using the cd command.
# explicit relative paths, from /
## Code
```
hacker@paths~explicit-relative-paths-from-:~$ cd /
hacker@paths~explicit-relative-paths-from-:/$ ./challenge/run
Correct!!!
./challenge/run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{UqKCbYU-oUZFie8aFLk1wfl81rn.dBTN1QDLyQzN0czW}
```
## Approach
As mentioned in description, the current working directory is /. Changed the cwd to / by using cd command. Invoked the program from / by executing the relative path ./challenge/run.<br>
This returned the flag **pwn.college{UqKCbYU-oUZFie8aFLk1wfl81rn.dBTN1QDLyQzN0czW}**
## Learning
Learnt to access programs by invoking their directories in relative paths and from specific paths that can be changed from the current directory by using the cd command. Every directory has two implicit entries that we can reference in paths: . and ... The first, ., refers right to the same directory, so ./challenge, ././challenge and challenge relative paths are all identical to each other.
# implicit relative path
## Code
```
hacker@paths~implicit-relative-path:~$ cd /challenge
hacker@paths~implicit-relative-path:/challenge$ ./run
Correct!!!
./run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{Yl63CM0a2O9QbCXxkPddYM5elV4.dFTN1QDLyQzN0czW}
```
## Approach
As mentioned in description, the current working directory is /challenge. Changed the cwd to /challenge by using cd command. Invoked the program from /challenge by executing the relative path ./run.<br>
This returned the flag **pwn.college{Yl63CM0a2O9QbCXxkPddYM5elV4.dFTN1QDLyQzN0czW}**
## Learning
Learnt to access programs by invoking their directories in relative paths and from specific paths that can be changed from the current directory by using the cd command. Every directory has two implicit entries that we can reference in paths: . and ... The first, ., refers right to the same directory, so ./run, ././run and run relative paths are all identical to each other.<br>
However, Linux explicitly avoids automatically looking in the current directory when you provide a "naked" path, ex- run. If Linux searched the current directory for programs every time we entered a naked path, we could accidentally execute programs in our current directory that happened to have the same names as core system utilities. Hence the usage of ./ is necessary.
# home sweet home
## Code
```
hacker@paths~home-sweet-home:~$ echo LOOK: ~
LOOK: /home/hacker
hacker@paths~home-sweet-home:~$ /challenge/run ~/r
Writing the file to /home/hacker/r!
... and reading it back to you:
pwn.college{EO_b_fcGO-7LODuNAnhkvvWjIoI.dNzM4QDLyQzN0czW}
```
## Approach
As mentioned in description, the current working directory is ~ i.e. the home directory. This is the default directory. Used the echo LOOK command to show that ~ expands to /home/hacker. Invoked the program by excuting /challenge/run ~/r, where ~/r is the argument, 3 characters long and is under the home directory ~. This wrote the file to ~/r or /home/hacker/r.<br>
This returned the flag **pwn.college{EO_b_fcGO-7LODuNAnhkvvWjIoI.dNzM4QDLyQzN0czW}**
## Learning
The ~ in the default prompt represents the home directory /home/hacker and is the default current working directory. Expansion of ~ is an absolute path. cd will use the home directory as the default destination.
