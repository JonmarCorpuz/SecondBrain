# Install Apache (Ubuntu Server)

```Bash
#
sudo apt -y update && sudo apt -y upgrade

#
sudo apt -y install apache2

#
sudo ufw allow 'Apache'

#
sudo systemctl start apache2
sudo systemctl status apache2
```
