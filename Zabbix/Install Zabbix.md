# Install Zabbix

```Bash
sudo apt -y update && sudo apt -y upgrade
```

Ubuntu 22.04
```Bash
sudo wget https://repo.zabbix.com/zabbix/5.0/ubuntu/pool/main/z/zabbix-release/zabbix-release_5.0-1+focal_all.deb
sudo dpkg -i zabbix-release_5.0-1+focal_all.deb
sudo apt -y update && sudo apt -y upgrade
```

Ubuntu 24.04
```Bash
wget https://repo.zabbix.com/zabbix/6.0/ubuntu/pool/main/z/zabbix-release/zabbix-release_6.0-2%2Bubuntu24.04_all.deb
sudo dpkg -i zabbix-release_6.0-2+ubuntu24.04_all.deb
sudo apt -y update && sudo apt -y upgrade
```

```Bash
sudo apt -y install zabbix-server-mysql zabbix-frontend-php zabbix-apache-conf zabbix-agent mysql-server

sudo mysql_secure_installation

sudo mysql -u root -p 
CREATE DATABASE zabbixDB CHARACTER SET utf8 COLLATE utf8_bin;
CREATE USER zabbix@localhost IDENTIFIED BY 'StrongDBPassword';
GRANT ALL PRIVILEGES ON zabbixDB.* TO zabbix@localhost;
EXIT;

# The password is the password you gave for the database
zcat /usr/share/doc/zabbix-server-mysql/create.sql.gz | mysql -u zabbix -p zabbixDB
```

```Bash
# Uncomment timezone
sudo nano /etc/zabbix/apache.conf
```

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Zabbix%20Install%20pt5-2.jpg)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Zabbix%20Install%20pt5-3.jpg)

```Bash
# Ensure that the usernames and passwords match those of your mysql database
sudo nano /etc/zabbix/zabbix_server.conf
```

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Zabbix%20DB%20Password%20pt1.png)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Zabbix%20DB%20Password%20pt2.png)

```Bash
sudo systemctl restart apache2 zabbix-server.service
sudo systemctl enable apache2 zabbix-server.service
```

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Zabbix%20Install%20pt6.jpg)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Zabbix%20Install%20pt7.jpg)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Zabbix%20Install%20pt8.jpg)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Zabbix%20Install%20pt9.jpg)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Zabbix%20Install%20pt10.jpg)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Zabbix%20Install%20pt11.jpg)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Zabbix%20Install%20pt12.jpg)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Zabbix%20Install%20pt13.jpg)
