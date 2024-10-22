# Rsyslog Overview

The Rocket-fast System for LOG processing is a logging system used by many Linux distributions

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/ijbghadfihgfdvbafhvdisabfhsidafsashfgsfouh.png)

* Designed to handle large volumes of log data efficiently
* Can be configured to collect, process, and store logs from various sources across a network
* Can gather logs from a variety of sources (Ex: *Local system logs*, *Remote systems*, *Network devices*, *etc.*)
* Allows users to route logs based on various criteria (Ex: *Severity levels*, *Message contents*, *Originating hosts*, *etc.*)
* Can store logs locally or forward them to remote destinations (Ex: *Databases*, *Log management systems*, *Syslog servers*, *etc.*)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Rsyslog Components

## Configuration Files

Configuration files are typically located in **/etc/rsyslog.conf** and **/etc/rsyslog.d** and define Rsyslog's behavior (Ex: *Where log messages should be stored or forwarded to*, *What format should logs should be stored in*, *What actions should be taken based on a log's content*, *etc.*)

## Syslog Daemon

The Sysmon daemon is the core component of Rsyslog that's responsible for receiving, processing, and forwarding log messages

* Listens for incoming log messages on various channels or sockets
* Applies the processing rules defined in its configuration
