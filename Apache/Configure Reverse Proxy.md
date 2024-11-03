# Configure Reverse Proxy (Ubuntu Server)

```Bash
#
sudo apt -y update

#
sudo apt -y install apache2

#
sudo a2enmod proxy
sudo a2enmod proxy_http
sudo a2enmod proxy_balancer
sudo a2enmod lbmethod_byrequests

#
sudo nano /etc/apache2/sites-available/example.conf
```

```Text
<VirtualHost *:80>
    ServerName example.com

    ProxyPass / http://localhost:8080/
    ProxyPassReverse / http://localhost:8080/
</VirtualHost>
```

```Bash
#
sudo a2ensite example.conf

#
sudo systemctl reload apache2
```
