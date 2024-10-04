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
# listing files
## Code
```
hacker@commands~listing-files:~$ ls /challenge
12323-renamed-run-355  DESCRIPTION.md
hacker@commands~listing-files:~$ /challenge/12323-renamed-run-355
Yahaha, you found me! Here is your flag:
pwn.college{Ez2YPFGX_wcoICSDWmyYZ3BzqdH.dhjM4QDLyQzN0czW}
```
## Approach
The program /challenge/flag was renamed to a random name. Listed the files in /challenge to obtain a file 12323-renamed-run-355. Invoked the file through the absolute path /challenge/12323-renamed-run-355.<br>
This returned the flag **pwn.college{Ez2YPFGX_wcoICSDWmyYZ3BzqdH.dhjM4QDLyQzN0czW}**
## Learning
Learnt to list files in a directory using the ls command in Linux.
# touching files
## Code
```
hacker@commands~touching-files:~$ cd /tmp
hacker@commands~touching-files:/tmp$ ls
bin  hsperfdata_root  tmp.G9qthVCks5
hacker@commands~touching-files:/tmp$ touch pwn
hacker@commands~touching-files:/tmp$ touch college
hacker@commands~touching-files:/tmp$ ls
bin  college  hsperfdata_root  pwn  tmp.G9qthVCks5
hacker@commands~touching-files:/tmp$ /challenge/run
Success! Here is your flag:
pwn.college{IUvvYADYmrLmBLqC3gw5O5FOmfY.dBzM4QDLyQzN0czW}
```
## Approach
Changed the directory to tmp as we had to add files as absolute paths /tmp/pwn and /tmp/college. The /tmp directory already contained three files. We checked this using the ls command. Used touch command to add files pwn and college. Now, using the ls command again, we see that two more files have been added, which are pwn and college. Finally, run the program /challenge/run.<br>
This returned the flag **pwn.college{IUvvYADYmrLmBLqC3gw5O5FOmfY.dBzM4QDLyQzN0czW}**
## Learning
Learnt to use ls and touch commands to list and add new files in a directory.
# removing files
## Code
```
hacker@commands~removing-files:~$ ls
Desktop  delete_me  r
hacker@commands~removing-files:~$ rm delete_me
hacker@commands~removing-files:~$ /challenge/check
Excellent removal. Here is your reward:
pwn.college{84W0VUnaQqBB3Z4Qg9_WECxCmv_.dZTOwUDLyQzN0czW}
```
## Approach
Checked the list of files in the home directory using the ls command. The delete_me file existed. Used the rm command to delete this file. Now executed the /challenge/check command which made sure we deleted it.<br>
This returned the flag **pwn.college{84W0VUnaQqBB3Z4Qg9_WECxCmv_.dZTOwUDLyQzN0czW}**
## Learning
Learnt to use the rm command to delete files in a directory.
# hidden files
## Code
```
hacker@commands~hidden-files:~$ ls /
bin   challenge  etc   lib    lib64   media  nix  proc  run   srv  tmp  var
boot  dev        home  lib32  libx32  mnt    opt  root  sbin  sys  usr
hacker@commands~hidden-files:~$ ls / -a
.   .dockerenv            bin   challenge  etc   lib    lib64   media  nix  proc  run   srv  tmp  var
..  .flag-15613129679998  boot  dev        home  lib32  libx32  mnt    opt  root  sbin  sys  usr
hacker@commands~hidden-files:~$ cat /.flag-15613129679998
pwn.college{MgNGKiJxZWoAW_MsHjGNl-scyQD.dBTN4QDLyQzN0czW}
```
## Approach
Checked the list of files in / using the ls command. The files were not dot-prepended. Used the ls -a command to list all files in the directory, including the ones dot-pretended. Now executed the cat command on .flag-15613129679998 file as cat /.flag-15613129679998 to read the file.<br>
This returned the flag **pwn.college{84W0VUnaQqBB3Z4Qg9_WECxCmv_.dZTOwUDLyQzN0czW}**
## Learning
ls doesn't list all the files by default. Linux has a convention where files that start with a . don't show up by default in ls and in a few other contexts. Learnt to use the ls -a command to list hidden files in a directory, like dot-pretended files.
# An Epic Filesystem Quest
## Code
```
hacker@commands~an-epic-filesystem-quest:~$ ls /
GIST  boot       dev  flag  lib    lib64   media  nix  proc  run   srv  tmp  var
bin   challenge  etc  home  lib32  libx32  mnt    opt  root  sbin  sys  usr
hacker@commands~an-epic-filesystem-quest:~$ cat /GIST
Great sleuthing!
The next clue is in: /usr/local/lib/python3.8/dist-packages/ipywidgets/widgets/__pycache__

The next clue is **hidden** --- its filename starts with a '.' character. You'll need to look for it using special options to 'ls'.
hacker@commands~an-epic-filesystem-quest:~$ cd /usr/local/lib/python3.8/dist-packages/ipywidgets/widgets/__pycache__
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/ipywidgets/widgets/__pycache__$ ls -a
.                           widget_box.cpython-38.pyc          widget_media.cpython-38.pyc
..                          widget_button.cpython-38.pyc       widget_output.cpython-38.pyc
.MESSAGE                    widget_color.cpython-38.pyc        widget_selection.cpython-38.pyc
__init__.cpython-38.pyc     widget_controller.cpython-38.pyc   widget_selectioncontainer.cpython-38.pyc
docutils.cpython-38.pyc     widget_core.cpython-38.pyc         widget_string.cpython-38.pyc
domwidget.cpython-38.pyc    widget_date.cpython-38.pyc         widget_style.cpython-38.pyc
interaction.cpython-38.pyc  widget_datetime.cpython-38.pyc     widget_tagsinput.cpython-38.pyc
trait_types.cpython-38.pyc  widget_description.cpython-38.pyc  widget_templates.cpython-38.pyc
utils.cpython-38.pyc        widget_float.cpython-38.pyc        widget_time.cpython-38.pyc
valuewidget.cpython-38.pyc  widget_int.cpython-38.pyc          widget_upload.cpython-38.pyc
widget.cpython-38.pyc       widget_layout.cpython-38.pyc
widget_bool.cpython-38.pyc  widget_link.cpython-38.pyc
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/ipywidgets/widgets/__pycache__$ cat .MES
SAGE
Yahaha, you found me!
The next clue is in: /usr/share/racket/pkgs/srfi-lib/srfi/42/compiled

Watch out! The next clue is **trapped**. You'll need to read it out without 'cd'ing into the directory; otherwise, the clue will self destruct!
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/ipywidgets/widgets/__pycache__$ ls -a /u
sr/share/racket/pkgs/srfi-lib/srfi/42/compiled
.                             dispatching_scm.zo        extra-generators_scm.zo        loops_scm.zo
..                            ec-core_scm.dep           generator-definitions_scm.dep  mzscheme2_rkt.dep
POINTER-TRAPPED               ec-core_scm.zo            generator-definitions_scm.zo   mzscheme2_rkt.zo
comprehension-struct_scm.dep  ec_rkt.dep                generator-struct_scm.dep       simplifier_scm.dep
comprehension-struct_scm.zo   ec_rkt.zo                 generator-struct_scm.zo        simplifier_scm.zo
comprehensions_scm.dep        expansion_scm.dep         generators_scm.dep
comprehensions_scm.zo         expansion_scm.zo          generators_scm.zo
dispatching_scm.dep           extra-generators_scm.dep  loops_scm.dep
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/ipywidgets/widgets/__pycache__$ cat /usr/share/racket/pkgs/srfi-lib/srfi/42/compiled/POINTER-TRAPPED
Tubular find!
The next clue is in: /usr/share/javascript/mathjax/unpacked/jax/output/SVG/fonts/Gyre-Termes/Monospace/Regular

The next clue is **delayed** --- it will not become readable until you enter the directory with 'cd'.
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/ipywidgets/widgets/__pycache__$ cd /usr/share/javascript/mathjax/unpacked/jax/output/SVG/fonts/Gyre-Termes/Monospace/Regular
hacker@commands~an-epic-filesystem-quest:/usr/share/javascript/mathjax/unpacked/jax/output/SVG/fonts/Gyre-Termes/Monospace/Regular$ ls -a
.  ..  Main.js  NUGGET
hacker@commands~an-epic-filesystem-quest:/usr/share/javascript/mathjax/unpacked/jax/output/SVG/fonts/Gyre-Termes/Monospace/Regular$ cat NUGGET
Lucky listing!
The next clue is in: /usr/share/perl/5.30.0/IPC
hacker@commands~an-epic-filesystem-quest:/usr/share/javascript/mathjax/unpacked/jax/output/SVG/fonts/Gyre-Termes/Monospace/Regular$ cd /usr/share/perl/5.30.0/IPC
hacker@commands~an-epic-filesystem-quest:/usr/share/perl/5.30.0/IPC$ ls -a
.  ..  Cmd.pm  Open2.pm  Open3.pm  README
hacker@commands~an-epic-filesystem-quest:/usr/share/perl/5.30.0/IPC$ cat README
Yahaha, you found me!
The next clue is in: /usr/share/locale/bi

The next clue is **hidden** --- its filename starts with a '.' character. You'll need to look for it using special options to 'ls'.
hacker@commands~an-epic-filesystem-quest:/usr/share/perl/5.30.0/IPC$ cd /usr/share/locale/bi
hacker@commands~an-epic-filesystem-quest:/usr/share/locale/bi$ ls -a
.  ..  .TRACE  LC_MESSAGES
hacker@commands~an-epic-filesystem-quest:/usr/share/locale/bi$ cat .TRACE
Yahaha, you found me!
The next clue is in: /usr/local/lib/python3.8/dist-packages/jedi/third_party/typeshed/third_party/2and3/boto

The next clue is **delayed** --- it will not become readable until you enter the directory with 'cd'.
hacker@commands~an-epic-filesystem-quest:/usr/share/locale/bi$ cd /usr/local/lib/python3.8/dist-packages/jedi/third_party/typeshed/third_party/2and3/boto
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/jedi/third_party/typeshed/third_party/2and3/boto$ ls -a
.   BLUEPRINT     auth.pyi          compat.pyi      ec2  exception.pyi  plugin.pyi      s3
..  __init__.pyi  auth_handler.pyi  connection.pyi  elb  kms            regioninfo.pyi  utils.pyi
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/jedi/third_party/typeshed/third_party/2and3/boto$ cat BLUEPRINT
Great sleuthing!
The next clue is in: /opt/linux/linux-5.4/include/config/snd/jack

The next clue is **hidden** --- its filename starts with a '.' character. You'll need to look for it using special options to 'ls'.
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/jedi/third_party/typeshed/third_party/2and3/boto$ cd /opt/linux/linux-5.4/include/config/snd/jack
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/include/config/snd/jack$ ls -a
.  ..  .INFO  input
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/include/config/snd/jack$ cat .INFO
Congratulations, you found the clue!
The next clue is in: /usr/share/racket/pkgs/srfi-doc/srfi/scribblings/srfi-std/srfi-41
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/include/config/snd/jack$ cd /usr/share/racket/pkgs/srfi-doc/srfi/scribblings/srfi-std/srfi-41
hacker@commands~an-epic-filesystem-quest:/usr/share/racket/pkgs/srfi-doc/srfi/scribblings/srfi-std/srfi-41$ ls -a
.  ..  CUE  srfi-41.html  streams1.jpg  streams2.jpg
hacker@commands~an-epic-filesystem-quest:/usr/share/racket/pkgs/srfi-doc/srfi/scribblings/srfi-std/srfi-41$ cat CUE
CONGRATULATIONS! Your perserverence has paid off, and you have found the flag!
It is: pwn.college{s0JfaDqIx7Z4sxKzA3rvLcZoh1Y.dljM4QDLyQzN0czW}
```
## Approach

This returned the flag **pwn.college{s0JfaDqIx7Z4sxKzA3rvLcZoh1Y.dljM4QDLyQzN0czW}**
## Learning

# making directories
## Code
```
hacker@commands~making-directories:~$ cd /tmp
hacker@commands~making-directories:/tmp$ mkdir pwn
hacker@commands~making-directories:/tmp$ ls
bin  hsperfdata_root  pwn  tmp.G9qthVCks5
hacker@commands~making-directories:/tmp$ cd pwn
hacker@commands~making-directories:/tmp/pwn$ touch college
hacker@commands~making-directories:/tmp/pwn$ ls
college
hacker@commands~making-directories:/tmp/pwn$ /challenge/run
Success! Here is your flag:
pwn.college{gzxlgmF0M7Zh_YI5pQdxIlyvyJp.dFzM4QDLyQzN0czW}
```
## Approach

This returned the flag **pwn.college{gzxlgmF0M7Zh_YI5pQdxIlyvyJp.dFzM4QDLyQzN0czW}**
## Learning

# finding files
## Code
```
hacker@commands~finding-files:~$ ls -a
.  ..  .ICEauthority  .bash_history  .bash_logout  .bashrc  .cache  .config  .dbus  .local  .profile  Desktop  r
hacker@commands~finding-files:~$ find -name flag
hacker@commands~finding-files:~$ cd /
hacker@commands~finding-files:/$ ls -a
.   .dockerenv  boot       dev  home  lib32  libx32  mnt  opt   root  sbin  sys  usr
..  bin         challenge  etc  lib   lib64  media   nix  proc  run   srv   tmp  var
hacker@commands~finding-files:/$ find -name flag
find: ‘./root’: Permission denied
find: ‘./etc/ssl/private’: Permission denied
find: ‘./tmp/tmp.G9qthVCks5’: Permission denied
./usr/local/share/radare2/5.9.5/flag
./usr/local/lib/python3.8/dist-packages/pwnlib/flag
find: ‘./var/cache/apt/archives/partial’: Permission denied
find: ‘./var/cache/ldconfig’: Permission denied
find: ‘./var/cache/private’: Permission denied
find: ‘./var/log/private’: Permission denied
find: ‘./var/log/apache2’: Permission denied
find: ‘./var/log/mysql’: Permission denied
find: ‘./var/lib/apt/lists/partial’: Permission denied
find: ‘./var/lib/mysql-keyring’: Permission denied
find: ‘./var/lib/php/sessions’: Permission denied
find: ‘./var/lib/private’: Permission denied
find: ‘./var/lib/mysql-files’: Permission denied
find: ‘./var/lib/mysql’: Permission denied
find: ‘./run/mysqld’: Permission denied
find: ‘./run/sudo’: Permission denied
find: ‘./proc/tty/driver’: Permission denied
find: ‘./proc/1/task/1/fd’: Permission denied
find: ‘./proc/1/task/1/fdinfo’: Permission denied
find: ‘./proc/1/task/1/ns’: Permission denied
find: ‘./proc/1/fd’: Permission denied
find: ‘./proc/1/map_files’: Permission denied
find: ‘./proc/1/fdinfo’: Permission denied
find: ‘./proc/1/ns’: Permission denied
find: ‘./proc/7/task/7/fd’: Permission denied
find: ‘./proc/7/task/7/fdinfo’: Permission denied
find: ‘./proc/7/task/7/ns’: Permission denied
find: ‘./proc/7/fd’: Permission denied
find: ‘./proc/7/map_files’: Permission denied
find: ‘./proc/7/fdinfo’: Permission denied
find: ‘./proc/7/ns’: Permission denied
./opt/capstone/tests/MC/AArch64/SME2p1/flag
./opt/pwndbg/.venv/lib/python3.8/site-packages/pwnlib/flag
./opt/radare2/libr/flag
./nix/store/pmvk2bk4p550w182rjfm529kfqddnvh3-python3.11-pwntools-4.12.0/lib/python3.11/site-packages/pwnlib/flag
./nix/store/1yagn5s8sf7kcs2hkccgf8d0wxlrv5sz-radare2-5.9.0/share/radare2/5.9.0/flag
hacker@commands~finding-files:/$ cat /usr/local/share/radare2/5.9.5/flag
cat: /usr/local/share/radare2/5.9.5/flag: Is a directory
hacker@commands~finding-files:/$ cat ./usr/local/lib/python3.8/dist-packages/pwnlib/flag
cat: ./usr/local/lib/python3.8/dist-packages/pwnlib/flag: Is a directory
hacker@commands~finding-files:/$ cat ./opt/capstone/tests/MC/AArch64/SME2p1/flag
pwn.college{ku6CRt5i_s0mI-T-WL2CjAJG5ea.dJzM4QDLyQzN0czW}
```
## Approach

This returned the flag **pwn.college{ku6CRt5i_s0mI-T-WL2CjAJG5ea.dJzM4QDLyQzN0czW}**
## Learning

# linking files
## Code
```
hacker@commands~linking-files:~$ ln -s /flag /home/hacker/not-the-flag
ln: failed to create symbolic link '/home/hacker/not-the-flag': File exists
hacker@commands~linking-files:~$ rm /home/hacker/not-the-flag
hacker@commands~linking-files:~$ ln -s /flag /home/hacker/not-the-flag
hacker@commands~linking-files:~$ /challenge/catflag
About to read out the /home/hacker/not-the-flag file!
pwn.college{AtimxXUFzctgkNBYs0dISq9e8CL.dlTM1UDLyQzN0czW}
```
## Approach

This returned the flag **pwn.college{AtimxXUFzctgkNBYs0dISq9e8CL.dlTM1UDLyQzN0czW}**
## Learning
