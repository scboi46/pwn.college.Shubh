# 1. Matching with *

Challenge Description : The first glob we'll learn is *. When it encounters a * character in any argument, the shell will treat it as a "wildcard" and try to replace that argument with any files that match the pattern. It's easier to show you than explain:

hacker@dojo:~$ touch file_a
hacker@dojo:~$ touch file_b
hacker@dojo:~$ touch file_c
hacker@dojo:~$ ls
file_a	file_b	file_c
hacker@dojo:~$ echo Look: file_*
Look: file_a file_b file_c
Of course, though in this case, the glob resulted in multiple arguments, it can just as simply match only one. For example:

hacker@dojo:~$ touch file_a
hacker@dojo:~$ ls
file_a
hacker@dojo:~$ echo Look: file_*
Look: file_a
When zero files are matched, by default, the shell leaves the glob unchanged:

hacker@dojo:~$ touch file_a
hacker@dojo:~$ ls
file_a
hacker@dojo:~$ echo Look: nope_*
Look: nope_*
The * matches any part of the filename except for / or a leading . character. For example:

hacker@dojo:~$ echo ONE: /ho*/*ck*
ONE: /home/hacker
hacker@dojo:~$ echo TWO: /*/hacker
TWO: /home/hacker
hacker@dojo:~$ echo THREE: ../*
THREE: ../hacker
Now, practice this yourself! Starting from your home directory, change your directory to /challenge, but use globbing to keep the argument you pass to cd to at most four characters! Once you're there, run /challenge/run for the flag!


## My Solve
**Flag:** `pwn.college{UrqWMVqBjPK_1VO1n8i0YjWLxiY.QXxIDO0wCN2EzNzEzW}`

```
hacker@globbing~matching-with-:~$ cd /ch*
hacker@globbing~matching-with-:/challenge$ /challenge/run
You ran me with the working directory of /challenge! Here is your flag:
pwn.college{UrqWMVqBjPK_1VO1n8i0YjWLxiY.QXxIDO0wCN2EzNzEzW}

```

## What I learned
When it encounters a * character in any argument, the shell will treat it as a "wildcard" and try to replace that argument with any files that match the pattern.


# 2. Matching with ?

Challenge Description : Next, let's learn about ?. When it encounters a ? character in any argument, the shell will treat it as a single-character wildcard. This works like *, but only matches one character. For example:

hacker@dojo:~$ touch file_a
hacker@dojo:~$ touch file_b
hacker@dojo:~$ touch file_cc
hacker@dojo:~$ ls
file_a	file_b	file_cc
hacker@dojo:~$ echo Look: file_?
Look: file_a file_b
hacker@dojo:~$ echo Look: file_??
Look: file_cc
Now, practice this yourself! Starting from your home directory, change your directory to /challenge, but use the ? character instead of c and l in the argument to cd! Once you're there, run /challenge/run for the flag!


## My solve
**Flag:** `pwn.college{YPEln-ezFnr2yZDU0BySGqvjcO7.QXyIDO0wCN2EzNzEzW}`


```
hacker@globbing~matching-with-:~$ cd /?ha??enge
hacker@globbing~matching-with-:/challenge$ /challenge/run
You ran me with the working directory of /challenge! Here is your flag:
pwn.college{YPEln-ezFnr2yZDU0BySGqvjcO7.QXyIDO0wCN2EzNzEzW}

```

## What I learned

When it encounters a ? character in any argument, the shell will treat it as a single-character wildcard. This works like *, but only matches one character.


# 3. Matching with []

Challenge Description : Next, we will cover []. The square brackets are, essentially, a limited form of ?, in that instead of matching any character, [] is a wildcard for some subset of potential characters, specified within the brackets. For example, [pwn] will match the character p, w, or n. For example:

hacker@dojo:~$ touch file_a
hacker@dojo:~$ touch file_b
hacker@dojo:~$ touch file_c
hacker@dojo:~$ ls
file_a	file_b	file_c
hacker@dojo:~$ echo Look: file_[ab]
Look: file_a file_b
Try it here! We've placed a bunch of files in /challenge/files. Change your working directory to /challenge/files and run /challenge/run with a single argument that bracket-globs into file_b, file_a, file_s, and file_h!


## My solve
**Flag:** `pwn.college{IVRdAVGLBP2Z3CN50-QB5b5Krq7.QXzIDO0wCN2EzNzEzW}`

```
hacker@globbing~matching-with-:/challenge/files$ /challenge/run file_[absh]
You got it! Here is your flag!
pwn.college{IVRdAVGLBP2Z3CN50-QB5b5Krq7.QXzIDO0wCN2EzNzEzW}

```

## What I learned
The square brackets are, essentially, a limited form of ?, in that instead of matching any character, [] is a wildcard for some subset of potential characters, specified within the brackets.


# 4. Matching paths with []

Challenge Description : Globbing happens on a path basis, so you can expand entire paths with your globbed arguments. For example:

hacker@dojo:~$ touch file_a
hacker@dojo:~$ touch file_b
hacker@dojo:~$ touch file_c
hacker@dojo:~$ ls
file_a	file_b	file_c
hacker@dojo:~$ echo Look: /home/hacker/file_[ab]
Look: /home/hacker/file_a /home/hacker/file_b
Now it's your turn. Once more, we've placed a bunch of files in /challenge/files. Starting from your home directory, run /challenge/run with a single argument that bracket-globs into the absolute paths to the file_b, file_a, file_s, and file_h files!


## My solve
**Flag:** `pwn.college{QdfupmASWTbkSvY374nFfu5XjGy.QX0IDO0wCN2EzNzEzW}`

```
hacker@globbing~matching-paths-with-:~$ /challenge/run /challenge/files/file_[bash]
You got it! Here is your flag!
pwn.college{QdfupmASWTbkSvY374nFfu5XjGy.QX0IDO0wCN2EzNzEzW}

```

## What I learned
Globbing happens on a path basis, so you can expand entire paths with your globbed arguments.


# 5. Multiple Globs

Challenge Description : So far, you've specified one glob at a time, but you can do more! Bash supports the expansion of multiple globs in a single word. For example:

hacker@dojo:~$ cat /*fl*
pwn.college{YEAH}
hacker@dojo:~$
What happens above is that the shell looks for all files in / that start with anything (including nothing), then have an f and an l, and end in anything (including ag, which makes flag).

Now you try it. We put a few happy, but diversely-named files in /challenge/files. Go cd there and run /challenge/run, providing a single argument: a short (3 characters or less) globbed word with two * globs in it that covers every word that contains the letter p.


## My solve
**Flag:** `pwn.college{kkrIZ5eKFrByr75c2k2L3MMm2R4.0lM3kjNxwCN2EzNzEzW}`

```
hacker@globbing~multiple-globs:~$ cd /challenge/files
hacker@globbing~multiple-globs:/challenge/files$ /challenge/run *p*
You got it! Here is your flag!
pwn.college{kkrIZ5eKFrByr75c2k2L3MMm2R4.0lM3kjNxwCN2EzNzEzW}

```

## What I learned
The shell looks for all files in / that start with anything (including nothing), then have an f and an l, and end in anything (including ag, which makes flag).


# 6. Mixing globs

Challenge Description : Now, let's put the previous levels together! We put a few happy, but diversely-named files in /challenge/files. Go cd there and, using the globbing you've learned, write a single, short (6 characters or less) glob that (when passed as an argument to /challenge/run) will match the files "challenging", "educational", and "pwning"!

## My solve
**Flag:** `pwn.college{UP-TxGpOCpGj1t1MxOcgRETn-Tj.QX1IDO0wCN2EzNzEzW}`

```
hacker@globbing~mixing-globs:~$ cd /challenge/files
hacker@globbing~mixing-globs:/challenge/files$ /challenge/run [cpe]*
You got it! Here is your flag!
pwn.college{UP-TxGpOCpGj1t1MxOcgRETn-Tj.QX1IDO0wCN2EzNzEzW}

```

## What I learned
Globbing can be very helpful for finding data.


# 7. Exclusionary Globbing

Challenge Description : Sometimes, you want to filter out files in a glob! Luckily, [] helps you do just this. If the first character in the brackets is a ! or (in newer versions of bash) a ^, the glob inverts, and that bracket instance matches characters that aren't listed. For example:

hacker@dojo:~$ touch file_a
hacker@dojo:~$ touch file_b
hacker@dojo:~$ touch file_c
hacker@dojo:~$ ls
file_a	file_b	file_c
hacker@dojo:~$ echo Look: file_[!ab]
Look: file_c
hacker@dojo:~$ echo Look: file_[^ab]
Look: file_c
hacker@dojo:~$ echo Look: file_[ab]
Look: file_a file_b
Armed with this knowledge, go forth to /challenge/files and run /challenge/run with all files that don't start with p, w, or n!

NOTE: The ! character has a different special meaning in bash when it's not the first character of a [] glob, so keep that in mind if things stop making sense! ^ does not have this problem, but is also not compatible with older shells.


## My solve
**Flag:** `pwn.college{00XD4OIwvjkqGaINL02DfvUIsj2.QX2IDO0wiN0EzNzEzW}`

```
hacker@globbing~exclusionary-globbing:/challenge/files$ /challenge/run [!pwn]*
You got it! Here is your flag!
pwn.college{00XD4OIwvjkqGaINL02DfvUIsj2.QX2IDO0wiN0EzNzEzW}

```

## What I learned
 [] helps you do just this. If the first character in the brackets is a ! or (in newer versions of bash) a ^, the glob inverts, and that bracket instance matches characters that aren't listed.