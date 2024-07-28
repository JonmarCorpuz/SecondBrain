A remote shell is method used by threat actors to execute commands on a remote system as if they were operating directly on that system

* Change your terminal tty size with `stty {rows|cols} <number>`

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Remote Shell Connection Types

| Remote Shell Connection Type | Description |
| --- | --- |
| Bind Shell | The target host opens a port that the attacking host will connect to |
| Reverse Shell | The attacking host opens a port that the target host will connect to |

## Bind Shell

A bind shell is a type of shell where the target host opens a port that the attacking host will connect to

* The target executes code that starts up a listener on a port on their machine
* Can be prevented by firewalls

## Reverse Shell

A reverse shell is a type of shell where the attacking host opens a port that the target host will connect to

 * The target is forced to execute code that connects back to your computer
 * A good way to bypass firewall rules that may prevent you from connecting to arbitrary ports on the target
 * Receiving a shell from a machine across the internet requires you to configure your own network to accept the shell

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Shell Types

| Shell Type | Description |
| --- | --- |
| Non-Interactive Shell | Allows you to use programs that don't require user interaction in order to run properly |
| Interactive Shell | Allows you to interact with programs after executing them |

## Non-Interactive Shell

## Interactive Shell
