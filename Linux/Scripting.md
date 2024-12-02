# Scripting Overview

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Bash Script Elements

## Shebang

The shebang declares the interpreter to use for the script

```Bash
#!/bin/bash
```

## Arguments

* `$@` refers to all arguments passed in
* `$#` refers to the total number of arguments passed in
* `$$` refers to the current process ID for the job that's running the script

## Environmental Variables

* `PATH=<VALUE>`
* Variables that aren't input parameters are global to the entire script (If you want other programs to use the variable as well, you need to export the variable using `export <VARIABLE>=<VALUE>`
