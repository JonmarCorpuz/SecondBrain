Syslog is a protocol that's used to keep logs of various events that happen on the device

* Can be used on network devices to log events (Ex: *Interface status changes*, *OSPF neighbor status changes*, *System restarts*, *etc.*)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Syslog Message Format

seq:time stamp: %facility-severity-MNEMONIC:description

* **seq** refers to a sequence number that indicates the order and sequence of the log messages
* **time stamp** indicates the time the message was generated
* **facility** refers to a value that indicates which process on the device generated the message
* severity refers to a number that indicates the severity of the logged event
* MNEMONIC refers to a short code for the message that indicates what happened
* description refers to detailed information about the event that's being reported

## Syslog Severity Levels

The syslog severity level indicates how severe an event is

* Each severity has a number (0 being the most severe and 7 being the least severe)
* Because severities are very subjective, a relay or collector shouldn't assume that all originators have the same definition of severity (Each vendor may interpret each level differently)

| Syslog Severity Level | Keyword | Description |
| --- | --- | --- |
| 0 | Emergency | System is unusable |
| 1 | Alert | Action must be taken immediately |
| 2 | Critical | Critical conditions |
| 3 | Error | Error conditions |
| 4 | Warning | Warning conditions |
| 5 | Notice | Normal but significant condition |
| 6 | Informational | Information messages |
| 7 | Debugging | Debug-level messages |
