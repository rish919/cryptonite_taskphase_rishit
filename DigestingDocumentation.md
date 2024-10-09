# Learning from Documentation
## Code
```
hacker@man~learning-from-documentation:~$ /challenge/challenge --giveflag
Correct argument! Here is your flag:
pwn.college{U5BVjDx4hHpXXLU-u1ztAhFY6nt.dRjM5QDLyQzN0czW}
```
## Approach
.<br>
This returned the flag **pwn.college{U5BVjDx4hHpXXLU-u1ztAhFY6nt.dRjM5QDLyQzN0czW}**
## Learning

# Learning Complex Usage
## Code
```
hacker@man~learning-complex-usage:~$ /challenge/challenge --printfile /flag
Correct argument! Here is the /flag file:
pwn.college{Aq6w1zhyO3ImdLRIAiw8XUJXoxY.dVjM5QDLyQzN0czW}
```
## Approach
.<br>
This returned the flag **pwn.college{Aq6w1zhyO3ImdLRIAiw8XUJXoxY.dVjM5QDLyQzN0czW}
**
## Learning

# Reading Manuals
## Code
```
hacker@man~reading-manuals:~$ man challenge

CHALLENGE(1)                                      Challenge Commands                                     CHALLENGE(1)

NAME
       /challenge/challenge - print the flag!

SYNOPSIS
       challenge OPTION

DESCRIPTION
       Output the flag when called with the right arguments.

       --fortune
              read a fortune

       --version
              output version information and exit

       --telhnf NUM
              print the flag if NUM is 441

AUTHOR
       Written by Zardus.

REPORTING BUGS
       The repository for this dojo: <https://github.com/pwncollege/linux-luminarium/>

SEE ALSO
       man(1) bash-builtins(7)

pwn.college                                            May 2024                                          CHALLENGE(1)
hacker@man~reading-manuals:~$ /challenge/challenge --telhnf 441
Correct usage! Your flag: pwn.college{EDte4_R4HlQhnfic_PxXAQf1T76.dRTM4QDLyQzN0czW}
```
## Approach
.<br>
This returned the flag **pwn.college{EDte4_R4HlQhnfic_PxXAQf1T76.dRTM4QDLyQzN0czW}**
## Learning

# Searching Manuals
## Code
```
hacker@man~searching-manuals:~$ man challenge
hacker@man~searching-manuals:~$ /challenge/challenge --rxo
Initializing...
Correct usage! Your flag: pwn.college{URr3Bw06Kq2R8ZBlHvgnnud7leV.dVTM4QDLyQzN0czW}
```
## Approach
--rxo  This argument will give you the flag!.<br>
This returned the flag **pwn.college{URr3Bw06Kq2R8ZBlHvgnnud7leV.dVTM4QDLyQzN0czW}**
## Learning

# Searching for Manuals
## Code
```
hacker@man~searching-for-manuals:~$ man man
MAN(1)                                            Manual pager utils                                           MAN(1)

NAME
       man - an interface to the system reference manuals

SYNOPSIS
       man [man options] [[section] page ...] ...
       man -k [apropos options] regexp ...
       man -K [man options] [section] term ...
       man -f [whatis options] page ...
       man -l [man options] file ...
       man -w|-W [man options] page ...

DESCRIPTION
       man  is the system's manual pager.  Each page argument given to man is normally the name of a program, utility
       or function.  The manual page associated with each of these arguments is then found and displayed.  A section,
       if  provided,  will direct man to look only in that section of the manual.  The default action is to search in
       all of the available sections following a pre-defined order (see DEFAULTS), and to show only  the  first  page
       found, even if page exists in several sections.

       The table below shows the section numbers of the manual followed by the types of pages they contain.

       1   Executable programs or shell commands
       2   System calls (functions provided by the kernel)
       3   Library calls (functions within program libraries)
       4   Special files (usually found in /dev)
       5   File formats and conventions, e.g. /etc/passwd
       6   Games
       7   Miscellaneous (including macro packages and conventions), e.g. man(7), groff(7)
       8   System administration commands (usually only for root)
       9   Kernel routines [Non standard]

       A manual page consists of several sections.

       Conventional  section  names  include  NAME,  SYNOPSIS,  CONFIGURATION, DESCRIPTION, OPTIONS, EXIT STATUS, RE‐
       TURN VALUE, ERRORS, ENVIRONMENT, FILES, VERSIONS, CONFORMING TO, NOTES, BUGS, EXAMPLE, AUTHORS, and SEE ALSO.

       The following conventions apply to the SYNOPSIS section and can be used as a guide in other sections.

       bold text          type exactly as shown.
       italic text        replace with appropriate argument.
       [-abc]             any or all arguments within [ ] are optional.
       -a|-b              options delimited by | cannot be used together.
       argument ...       argument is repeatable.
       [expression] ...   entire expression within [ ] is repeatable.

       Exact rendering may vary depending on the output device.  For instance, man will usually not be able to render
       italics when running in a terminal, and will typically use underlined or coloured text instead.

       The  command  or function illustration is a pattern that should match all possible invocations.  In some cases
       it is advisable to illustrate several exclusive invocations as is shown in the SYNOPSIS section of this manual
       page.

EXAMPLES
       man ls
           Display the manual page for the item (program) ls.

       man man.7
           Display  the manual page for macro package man from section 7.  (This is an alternative spelling of "man 7
           man".)

       man 'man(7)'
           Display the manual page for macro package man from section 7.  (This is another  alternative  spelling  of
           "man  7  man".  It may be more convenient when copying and pasting cross-references to manual pages.  Note
           that the parentheses must normally be quoted to protect them from the shell.)

       man -a intro
           Display, in succession, all of the available intro manual pages contained within the manual.  It is possi‐
           ble to quit between successive displays or skip any of them.

       man -t bash | lpr -Pps
           Format  the  manual  page for bash into the default troff or groff format and pipe it to the printer named
           ps.  The default output for groff is usually PostScript.  man --help should advise as to  which  processor
           is bound to the -t option.

       man -l -Tdvi ./foo.1x.gz > ./foo.1x.dvi
           This command will decompress and format the nroff source manual page ./foo.1x.gz into a device independent
           (dvi) file.  The redirection is necessary as the -T flag causes output to be directed to  stdout  with  no
           pager.   The output could be viewed with a program such as xdvi or further processed into PostScript using
           a program such as dvips.

       man -k printf
           Search the short descriptions and manual page names for the keyword printf as regular  expression.   Print
           out any matches.  Equivalent to apropos printf.
hacker@man~searching-for-manuals:~$ man -k challenge
eencorslid (1)       - print the flag!
hacker@man~searching-for-manuals:~$ man eencorslid

CHALLENGE(1)                                      Challenge Commands                                     CHALLENGE(1)

NAME
       /challenge/challenge - print the flag!

SYNOPSIS
       challenge OPTION

DESCRIPTION
       Output the flag when called with the right arguments.

       --fortune
              read a fortune

       --version
              output version information and exit

       --eencor NUM
              print the flag if NUM is 486

AUTHOR
       Written by Zardus.

REPORTING BUGS
       The repository for this dojo: <https://github.com/pwncollege/linux-luminarium/>

SEE ALSO
       man(1) bash-builtins(7)
hacker@man~searching-for-manuals:~$ /challenge/challenge --eencor 486
Correct usage! Your flag: pwn.college{4UeEe8UnN6JNRJcorsHYlX8WiWR.dZTM4QDLyQzN0czW}
```
## Approach
.<br>
This returned the flag **pwn.college{4UeEe8UnN6JNRJcorsHYlX8WiWR.dZTM4QDLyQzN0czW}**
## Learning

# Helpful Programs
## Code
```
hacker@man~helpful-programs:~$ /challenge/challenge --help
usage: a challenge to make you ask for help [-h] [--fortune] [-v] [-g GIVE_THE_FLAG] [-p]

optional arguments:
  -h, --help            show this help message and exit
  --fortune             read your fortune
  -v, --version         get the version number
  -g GIVE_THE_FLAG, --give-the-flag GIVE_THE_FLAG
                        get the flag, if given the correct value
  -p, --print-value     print the value that will cause the -g option to give you the flag
hacker@man~helpful-programs:~$ /challenge/challenge -p
The secret value is: 369
hacker@man~helpful-programs:~$ /challenge/challenge -g 369
Correct usage! Your flag: pwn.college{EYhvKcXMqrI3xYcFSG6iZg9pJ8I.ddjM4QDLyQzN0czW}
```
## Approach
.<br>
This returned the flag **pwn.college{EYhvKcXMqrI3xYcFSG6iZg9pJ8I.ddjM4QDLyQzN0czW}**
## Learning

# Help for Builtins
## Code
```
hacker@man~help-for-builtins:~$ help challenge
challenge: challenge [--fortune] [--version] [--secret SECRET]
    This builtin command will read you the flag, given the right arguments!

    Options:
      --fortune         display a fortune
      --version         display the version
      --secret VALUE    prints the flag, if VALUE is correct

    You must be sure to provide the right value to --secret. That value
    is "gNmXrR2P".
hacker@man~help-for-builtins:~$ /challenge/challenge --secret gNmXrR2P
ssh-entrypoint: /challenge/challenge: No such file or directory
hacker@man~help-for-builtins:~$ challenge --secret gNmXrR2P
Correct! Here is your flag!
pwn.college{gNmXrR2PHw59pIi1iIouPE2jRDT.dRTM5QDLyQzN0czW}
```
## Approach
.<br>
This returned the flag **pwn.college{gNmXrR2PHw59pIi1iIouPE2jRDT.dRTM5QDLyQzN0czW}**
## Learning
