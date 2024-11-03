# Install TACACS+ (CentOS)

```Bash
cd /etc/yum.repos.d/

touch nux-misc.repo

echo "[nux-misc]" > nux-misc.repo
echo "name=Nux Misc" >> nux-misc.repo
echo "baseurl=http://li.nux.ro/download/nux/misc/el6/x86_64/" >> nux-misc.repo
echo "enabled=0" >> nux-misc.repo
echo "gpgcheck=1" >> nux-misc.repo
echo "gpgkey=http://li.nux.ro/download/nux/RPM-GPG-KEY-nux.ro" >> nux-misc.repo

yum --enablerepo=nux-misc install tac_plus
```
