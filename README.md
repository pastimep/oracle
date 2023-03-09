# oracle
1:开启root登入
sudo su
cd /root

修改authorized_keys文件（即ssh证书）
vi .ssh/authorized_keys
把ssh-rsa之前的文件都删除掉.
编辑ssh配置文件
nano /etc/ssh/sshd_config
找到PermitRootLogin, 把前面的#去掉 改成下面这样
PermitRootLogin yes
ctrl+x 保存退出 选择y 然后回车
然后
reboot
重启服务器。就可以使用root用户名配合秘钥登入了

2:开启防火墙
iptables -P INPUT ACCEPT
iptables -P FORWARD ACCEPT
iptables -P OUTPUT ACCEPT
iptables -F
apt-get purge netfilter-persistent

reboot 重启
