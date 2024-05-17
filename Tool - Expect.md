Expect is a Bash CLI tool that automates the control of interactive applications (Ex: *SSH*, *Telnet*, *FTP*, *etc.*)

* Able to wait for patterns in the output of the controlled program and then respond based on those patterns (Ex: *Look for a password prompt from an SSH session and then automatically provide the password*, *etc.*)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Expect Commands

* `spawn <command>` starts a script or program
* `expect {<pattern>|eof}` waits for a specific pattern or an EOF from the output of the spawned command
* `send <string>` sends a string to the previously started process
* `interact` allows a user to manually interact with the previously spawned process
* `set <variable> <value>` assigns a value to a variable
* `expect_after <pattern> <action>` specifies whaat should happen if a pattern is seen after a certain point in the script
* `expect_before <pattern> <value>` specifies what should happen if a pattern is seen before a certain point in the script
* `exp_continue` tells Expect to continue processing the current expect command within an expect block, allowing it to match additional patterns
* `timeout` determines how long Expect should wait for a pattern before giving up
* `close` closes the connection to the previously spawned process

