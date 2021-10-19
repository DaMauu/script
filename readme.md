[sshport](https://raw.githubusercontent.com/O7Y0/script/main/sshport.sh)
1.如果提示没有安装wget输入以下命令
#安装wget
yum install wget
2.下载脚本
#下载脚本
wget https://raw.githubusercontent.com/O7Y0/script/main/sshport.sh
3.下载完成后输入以下命令
bash sshport.sh
一键修改ssh端口
一键修改ssh端口
4.把修改的ssh端口添加到防火墙的放行端口
一定要执行这一步
#如果防火墙使用的iptables（Centos 6），修改端口为50000
iptables -I INPUT -p tcp --dport 50000 -j ACCEPT
service iptables save
service iptables restart
#如果使用的是firewall（CentOS 7）
firewall-cmd --zone=public --add-port=50000/tcp --permanent 
firewall-cmd --reload
5.重启
reboot
6.使用修改后的端口登录
