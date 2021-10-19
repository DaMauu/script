# 宁的集散中心
![GitHub](https://img.shields.io/github/license/mashape/apistatus.svg)
[![GitHub stars](https://img.shields.io/github/stars/O7Y0/script.svg?style=popout&label=Stars)](https://github.com/O7Y0/script/stargazers)
[![GitHub forks](https://img.shields.io/github/forks/O7Y0/script.svg?style=popout&label=Fork)](https://github.com/O7Y0/script/fork)
## 脚本索引
* [***MJ相关***](#代理相关)
  * [sshport.sh](#sshport)
---

## MJ相关

## sshport.sh

- 脚本说明: Linux一键更换默认端口

#### 使用说明:
``` wget
wget:yum install wget
bash:wget -N --no-check-certificate https://raw.githubusercontent.com/O7Y0/script/main/sshport.sh && chmod +x sshport.sh && bash sshport.sh
port:50000（或者任意你稀罕的）
firewall:把修改的ssh端口添加到防火墙的放行端口,一定要执行这一步
#如果防火墙使用的iptables（Centos 6），修改端口为50000
iptables -I INPUT -p tcp --dport 50000 -j ACCEPT
service iptables save
service iptables restart
#如果使用的是firewall（CentOS 7）
firewall-cmd --zone=public --add-port=50000/tcp --permanent 
firewall-cmd --reload
reboot:reboot
使用修改后的端口登录
```
