# Expect Overview

Expect is a Bash CLI tool that automates the control of interactive applications (Ex: *SSH*, *Telnet*, *FTP*, *etc.*)

* Able to wait for patterns in the output of the controlled program and then respond based on those patterns (Ex: *Look for a password prompt from an SSH session and then automatically provide the password*, *etc.*)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Expect Commands

```Bash
# Start a script or program
spawn <command> 

# Wait for a specific pattern or an EOF from the output of the spawned command
expect {<pattern>|eof} 

# Send a string to the previously started process
send <string>

# Manually interact with the previously spawned process
interact 

# Assign a value to a variable
set <variable> <value>

# Specify what should happen if a pattern is seen after a certain point in the script
expect_after <pattern> <action> 

# Specify what should happen if a pattern is seen before a certain point in the script
expect_before <pattern> <value>

# Instruct Expect to continue processing the current expect command within an expect block, allowing it to match additional patterns
exp_continue

# Specify how long Expect should wait for a pattern before giving up
timeout

# Close the connection to the previously spawned process
close
```
