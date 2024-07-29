File permissions control the actions that can be performed on a file or directory by different users

# SUID 

Set User ID is a special type of file permission that's used in Unix and Unix-like operating systems to allow a program to run with the privileges of the file's owner, rather than with the privileges of the user who's running the program

```Bash
# List files that have SUID or SGID bits set
find / -type f -perm -04000 -ls 2>/dev/null
```
