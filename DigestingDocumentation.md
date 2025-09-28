# 1. Learning from Documentation
Challenge Description : The typical need you'll have for documentation is just to figure out how to use all these dang programs, and a specific case of that is figuring out what arguments to specify on the command line. This module will mostly dig into that concept, as a proxy for figuring out how to use the programs in general. Through the rest of the module, you'll go through various ways of asking the environment for help for the programs, but first, we'll dig into the concept of reading documentation.

The correct usage of programs depends, in a large part, on the proper specification of arguments to them. Recall the -a of ls -a in the hidden files challenge of the Basic Commands module: that -a was an argument that told ls to list out hidden files as well as non-hidden files. Because we wanted to list out hidden files, invoking ls with the -a argument was the correct way to use it in our scenario.

The program for this challenge is /challenge/challenge, and you'll need to invoke it properly in order for it to give you the flag. Let's pretend that this is its documentation:

Welcome to the documentation for /challenge/challenge! To properly run this program, you will need to pass it the argument of --giveflag. Good luck!

Given that knowledge, go get the flag!

**Flag:** `pwn.college{4tejV_rG4T_TfQsam9ZjszTAt5g.QX0ITO0wCN2EzNzEzW}`

## What I learned
I learnt the correct usage of programs depends, in a large part, on the proper specification of arguments to them.
Arguments like -a are necessary for proper functioning of commands.


2. Learning Complex Usage

Challenge Description : While using most commands is straightforward, the usage of some commands can get quite complex. For example, the arguments to commands like sed and awk, which we're definitely not getting into right now, are entire programs in an esoteric programming language! Somewhere on the spectrum between cd and awk are commands that take arguments to their arguments...

This sounds crazy, but you've already encountered this with the find level in Basic Commands. find has a -name argument, and the -name argument itself takes an argument specifying the name to search for. Many other commands are analogous.

Here is this level's documentation for /challenge/challenge:

Welcome to the documentation for /challenge/challenge! This program allows you to print arbitrary files to the terminal, when given the --printfile argument. The argument to the --printfile argument is the path of the flag to read. For example, /challenge/challenge --printfile /challenge/DESCRIPTION.md will print out the description of the level!

Given that documentation, go get the flag!


**Flag:** `pwn.college{4tejV_rG4T_TfQsam9ZjszTAt5g.QX0ITO0wCN2EzNzEzW}`

## What I learned

I learnt how to print arbitrary files to the terminal with --printfile


# 3. Reading Manuals

Challenge Description : This level introduces the man command. man is short for manual, and will display (if available) the manual of the command you pass as an argument. For example, let's say we wanted to learn about the yes command (yes, this is a real command):
You can scroll around the manpage with your arrow keys and PgUp/PgDn. When you're done reading the manpage, you can hit q to quit.

Manpages are stored in a centralized database. If you're curious, this database lives in the /usr/share/man directory, but you never need to interact with it directly: you just query it using the man command. The arguments to the man command aren't file paths, but just the names of the entries themselves (e.g., you run man yes to look up the yes manpage, rather than man /usr/bin/yes, which would be the actual path to the yes program but would result in man displaying garbage).

The challenge in this level has a secret option that, when you use it, will cause the challenge to print the flag. You must learn this option through the man page for challenge!

## My solve
**Flag:** `pwn.college{wkdpSsZ4MTfdGGjSoWrGpgse88O.QX0EDO0wCN2EzNzEzW}`

## What I learned
man is short for manual, and will display (if available) the manual of the command you pass as an argument.



# 4. Searching Manuals

Challenge Description : You can scroll man pages with the arrow keys (and PgUp/PgDn) and search with /. After searching, you can hit n to go to the next result and N to go to the previous result. Instead of /, you can use ? to search backwards!

Find the option that will give you the flag by reading the challenge man page. 

## My solve
**Flag:** `pwn.college{88UIdtAWFDr3zWdM_1HyUsEN0ln.QX1EDO0wiN0EzNzEzW}`

I was provided in the problem statement that by using man command , I can search for the flag.

```
```
## What I learned
We can scroll man pages with the arrow keys (and PgUp/PgDn) and search with /. After searching, we can hit n to go to the next result and N to go to the previous result. Instead of /, we can use ? to search backwards!

