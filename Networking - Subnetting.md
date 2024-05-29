Subnetting is a technique used to divide a single network into smaller and more manageable sub-networks in order to reduce network congestion and improve network performance

* Involves splitting an IP address space into multiple smaller subnets that are each identified by its own unique subnet mask
* Allows for better organization of network resources (Ex: *More efficient use of IP addresses*, *etc.*)
* Allows for better security (Ex: *Isolating parts of the network*, *etc.*)
* Each subnet is identified by a unique subnet mask, which determines the range of IP addresses that belong to that subnet

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Subnetting Method

## FLSM

Fixed Length Subnet Masking is a subnetting technique that's used to divide a network into subnets of equal size, each containing the same subnet mask

* Can lead to inefficient allocation of IP addresses

## VLSM

Variable Length Subnet Masking is a subnetting technique used to allocate IP addresses for efficiently 

* Allows for subnets of different sizes within the same network by using subnet masks of varying lengths

| CIDR | SUBNET MASK | WILDCARD MASK | NUMBER OF IP ADDRESSES	| NUMBER OF USABLE IP ADDRESSES |
| --- | --- | --- | --- | --- |
| /32 | 255.255.255.255 |	0.0.0.0 |	1 |	1 |
| /31 |	255.255.255.254 |	0.0.0.1 |	2 |	2 |
| /30 |	255.255.255.252 |	0.0.0.3 |	4 |	2 |
| /29 |	255.255.255.248 |	0.0.0.7 |	8 |	6 |
| /28 |	255.255.255.240 |	0.0.0.15 | 16 |	14 |
| /27 |	255.255.255.224 |	0.0.0.31 | 32 | 30 |
| /26 |	255.255.255.192 |	0.0.0.63 | 64 |	62 |
| /25 |	255.255.255.128 |	0.0.0.127 |	128 |	126 |
| /24 |	255.255.255.0 |	0.0.0.255 | 256 | 254 |
| /23 |	255.255.254.0 |	0.0.1.255 |	512 |	510 |
| /22 |	255.255.252.0 |	0.0.3.255 |	1,024 |	1,022 |
| /21 |	255.255.248.0 |	0.0.7.255 |	2,048 |	2,046 |
| /20 |	255.255.240.0 |	0.0.15.255 | 4,096 | 4,094 |
| /19 |	255.255.224.0 |	0.0.31.255 | 8,192 | 8,190 |
| /18 | 255.255.192.0 | 0.0.63.255 | 16,384 | 16,382 |
| /17 |	255.255.128.0 |	0.0.127.255 | 32,768 | 32,766 |
| /16 |	255.255.0.0 |	0.0.255.255 | 65,536 | 65,534 |
| /15 |	255.254.0.0 |	0.1.255.255 |	131,072 | 131,070 |
| /14 |	255.252.0.0 | 0.3.255.255 | 262,144 | 262,142 |
| /13 |	255.248.0.0 |	0.7.255.255 |	524,288 |	524,286 |
| /12 |	255.240.0.0 |	0.15.255.255 | 1,048,576 | 1,048,574 |
| /11 |	255.224.0.0 |	0.31.255.255 | 2,097,152 | 2,097,150 |
| /10 | 255.192.0.0 |	0.63.255.255 | 4,194,304 | 4,194,302 |
| /9 | 255.128.0.0 | 0.127.255.255 | 8,388,608 | 8,388,606 |
| /8 | 255.0.0.0 | 0.255.255.255 | 16,777,216 | 16,777,214 |
| /7 | 254.0.0.0 | 1.255.255.255 | 33,554,432 | 33,554,430 |
| /6 | 252.0.0.0 | 3.255.255.255 | 67,108,864 |	67,108,862 |
| /5 | 248.0.0.0 | 7.255.255.255 | 134,217,728 | 134,217,726 |
| /4 | 240.0.0.0 | 15.255.255.255 |	268,435,456 |	268,435,454 |
| /3 | 224.0.0.0 | 31.255.255.255 |	536,870,912 |	536,870,910 |
| /2 | 192.0.0.0 | 63.255.255.255 |	1,073,741,824 |	1,073,741,822 |
| /1 | 128.0.0.0 | 127.255.255.255 | 2,147,483,648 | 2,147,483,646 |
| /0 | 0.0.0.0 | 255.255.255.255 | 4,294,967,296 | 4,294,967,294 |
