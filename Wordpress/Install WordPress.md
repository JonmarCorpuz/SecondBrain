# Install WordPress

```Bash
sudo apt -y update

sudo apt -y install apache2 mysql-server php libapache2-mod-php php-mysql

sudo mysql_secure_installation

cd /tmp
wget https://wordpress.org/latest.tar.gz

tar -zxvf latest.tar.gz

sudo mv wordpress /var/www/html/

sudo chown -R www-data:www-data /var/www/html/wordpress
sudo chmod -R 755 /var/www/html/wordpress

#cd /var/www/html/wordpress
#cp wp-config-sample.php wp-config.php
#sudo nano wp-config.php

sudo mysql 

CREATE DATABASE wordpress;
CREATE USER 'wordpress'@'localhost' IDENTIFIED BY 'StrongDBPassword';
GRANT ALL PRIVILEGES ON wordpress.* TO 'wordpressuser'@'localhost';
FLUSH PRIVILEGES;
EXIT;
```
