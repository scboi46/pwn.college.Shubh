# 1. Redirecting output

Challenge Description : 


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