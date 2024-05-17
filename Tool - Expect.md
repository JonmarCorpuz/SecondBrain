Expect is a Bash CLI tool that automates the control of interactive applications (Ex: *SSH*, *Telnet*, *FTP*, *etc.*)

* Able to wait for patterns in the output of the controlled program and then respond based on those patterns (Ex: *Look for a password prompt from an SSH session and then automatically provide the password*, *etc.*)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Expect Commands

* `spawn <program>` starts a program
* `expect "<value>"` waits for a specific output
* `send "<value>"` sends an input to the program
