# Install Metasploit (Ubuntu Server)

```Bash
#
sudo apt -y update && sudo apt -y upgrade

#
sudo apt-get install -y curl gnupg2 build-essential libssl-dev libreadline-dev zlib1g-dev

#
curl https://raw.githubusercontent.com/rapid7/metasploit-omnibus/master/config/templates/metasploit-framework-wrappers/msfupdate.erb > msfinstall

#
chmod +x msfinstall
sudo ./msfinstall
```
