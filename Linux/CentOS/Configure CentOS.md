# Change IP Address

```Bash
#
sudo nano /etc/sysconfig/network-scripts/ifcfg-<interface_id>

# 
#DEVICE=<interface>
#BOOTPROTO=none
#ONBOOT=yes
#IPADDR=<ip_address>
#NETMASK=<subnet_mask>
#GATEWAY=<default_gateway>
#DNS1=8.8.8.8
#DNS2=8.8.4.4

#
sudo systemctl restart network
#
#sudo ifdown eth0 && sudo ifup eth0
```
or
```Bash
#
sudo yum -y install net-tools

#
sudo ifconfig <interface> <ip_address> netmask <subnet_mask>

#
sudo route add default gw <gateway_ip_address>
```
