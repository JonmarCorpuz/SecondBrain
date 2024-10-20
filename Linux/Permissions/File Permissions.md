# File Permissions

File permissions control the actions that can be performed on a file or directory by different users

| File Permission Category | Description |
| --- | --- |
| Owner | |
| Group | |
| Other | |

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/dfghghsgdgsfgfdgfdgfdfgdgfdgfd.png)

| File Permission | Meaning | Description |
| --- | --- | --- |
| r | Read | |
| w | Write | |
| x | Execute | |
| s | SUID/SGID | |
| t | Sticky Bit | |

## SUID 

Set User ID is a special file permission bit that's used to allow a program to run with the privileges of the file's owner, rather than with the privileges of the user who's running the program

```Bash
# List files that have SUID bits set
find / -type f -perm -04000 -ls 2>/dev/null
```

```Bash
# List files that have SUID bits set along with their owner
find / -type f -perm -04000 -exec ls -l {} \; 2>/dev/null
```

## SGID 

Set Group ID is a special file permission bit that's used to allow a program to run with the privileges of the file's group ownership, rather then with the privileges of the user's default group

```Bash
# Set the SGID bit on a file or directory
chmod g+s {<filename>|<directory>}
```

```Bash
# Remove the SGID bit from a file or directory
chmod g-s {<filename>|<directory>}
```

```Bash
# List files that have SUID bits set
find / -type f -perm -02000 -ls 2>/dev/null
```
