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

**Flag:** `pwn.college{wkdpSsZ4MTfdGGjSoWrGpgse88O.QX0EDO0wCN2EzNzEzW}`

## What I learned
man is short for manual, and will display (if available) the manual of the command you pass as an argument.



# 4. Searching Manuals

Challenge Description : You can scroll man pages with the arrow keys (and PgUp/PgDn) and search with /. After searching, you can hit n to go to the next result and N to go to the previous result. Instead of /, you can use ? to search backwards!

Find the option that will give you the flag by reading the challenge man page. 

**Flag:** `pwn.college{A9umteLt2I7M_ed4E7K1ydKLfRh.QX1EDO0wCN2EzNzEzW}`

```
```
## What I learned
I learnt you can use / to search.


# 5. Searching for manuals

Challenge Description : This level is tricky: it hides the manpage for the challenge by randomizing its name. Luckily, all of the manpages are gathered in a searchable database, so you'll be able to search the man page database to find the hidden challenge man page! To figure out how to search for the right manpage, read the man page manpage by doing: man man!

HINT 1: man man teaches you advanced usage of the man command itself, and you must use this knowledge to figure out how to search for the hidden manpage that will tell you how to use /challenge/challenge

HINT 2: though the manpage is randomly named, you still actually use /challenge/challenge to get the flag!

**Flag:** `pwn.college{k48tvYYtCpLY8IjEFZ1ZXm_xMQn.QX2EDO0wCN2EzNzEzW}`

```
```

## What I learned
I learnt how to use man man and then search for the flag.


# 6. Helpful Programs

Challenge Description : Some programs don't have a man page, but might tell you how to run them if invoked with a special argument. Usually, this argument is --help, but it can often be -h or, in rare cases, -?, help, or other esoteric values like /? (though that latter is more frequently encountered on Windows).

In this level, you will practice reading a program's documentation with --help. Try it out!

**Flag:** `pwn.college{skcFSBJvluIBxldG2L2w3c9Assk.QX3IDO0wCN2EzNzEzW}`

```
```

## What I learned
Some programs don't have a man page, but might tell you how to run them if invoked with a special argument. Usually, this argument is --help, but it can often be -h or, in rare cases, -?, help, or other esoteric values like /? 


# 7. Help for Builtins

Challenge Description : Some programs don't have a man page, but might tell you how to run them if invoked with a special argument. Usually, this argument is --help, but it can often be -h or, in rare cases, -?, help, or other esoteric values like /? (though that latter is more frequently encountered on Windows).

In this level, you will practice reading a program's documentation with --help. Try it out!

**Flag:** `pwn.college{EZFHIzO885EtWzodpxcy5ZI20pd.QX0ETO0wCN2EzNzEzW}`

```
```

## What I learned
Some commands, rather than being programs with man pages and help options, are built into the shell itself. These are called builtins. Builtins are invoked just like commands, but the shell handles them internally instead of launching other programs.
 

