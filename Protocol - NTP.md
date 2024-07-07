The Network Time Protocol is a protocol that's used to synchronize the clocks of devices over a network

* Enables accurate timekeeping between various devices by synchronizing their clocks with a reference time source
* All devices have an internal clock
* Having accurate time on a device is to have accurate logs
* Allows automatic syncing of time over a network
* Allows accuracy of time within 1 millisecond if the NTP server is in the same LAN or within 50 milliseconds if connecting to the NTP server over a WAN
* Uses UDP port 123 to communicate
* Only uses the UTC timezone
* Provides authentication to be configured in order to allow NTP clients to ensure that they only sync to the intended servers
* A loopback address can't be manually configured as the NTP reference clock

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# NTP Components

* Although the hardware calendar (built-in clock) is the default time-source, both the hardware calendar and software clock can be both configured separately
* Typically you'd want to synchronize the hardware calendar and software clock

## Reference Clock

A reference clock is a highly accurate timekeeping device that's used as a source of time synchronization for NTP servers and clients

* Reference clocks are stratum 0 within the NTP hierarchy because they're the closes to the time source since they're the time source
* Stratum 15 is the maximum, meaning that anything above that is considered unreliable and the device won't synchronize to it (Ex: *Stratum 1 NTP servers get their time from reference clocks since they're directly connected to them*, *Stratum 2 NTP servers get their time from stratum 1 NTP servers since they're connected to the servers and not the reference clock*, *etc.*)

## Hardware Calendar

* Tracks the data and time on the device regardless of the event
* Used to initialize the software clock when the system is restarted

## Software Clock

## NTP Clients

* Request the time from NTP servers
* An NTP client can be a NTP server at the same time
* Can sync to multiple NTP servers
* The client will ask all the configured NTP servers for the time and will select whichever gives the best quickest response

## NTP Servers

* The distance of an NTP server from the original reference clock is called stratum

### Primary NTP Servers

A primary NTP server gets the time directly from reference clocks 

* Directly connected to the reference clocks

### Secondary NTP Servers

A secondary NTP server gets the time from another NTP server

* Can operate in server mode and client mode at the same time

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# NTP Modes

## Server Mode

* The default stratum of the NTP master is 8

## Client Mode

## Symmetric Active Mode

* Devices can peer with devices at the same stratum to provide more accurate time and a backup in case they lose access to the lower stratum NTP server
