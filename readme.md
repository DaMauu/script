# 宁的集散中心
![GitHub](https://img.shields.io/github/license/mashape/apistatus.svg)
[![GitHub stars](https://img.shields.io/github/stars/O7Y0/script.svg?style=popout&label=Stars)](https://github.com/O7Y0/script/stargazers)
[![GitHub forks](https://img.shields.io/github/forks/O7Y0/script.svg?style=popout&label=Fork)](https://github.com/O7Y0/script/fork)
## 脚本索引
* [***MJ相关***](#代理相关)
  * [sshport.sh](#sshport)
  * [bbr.sh](#bbr)
  * [bench-cn.sh](#bench)
  * [bench-abroad.sh](#bench-abroad)
  * [memtester.cpp](#memtester)
  * [uping.py](#uping)
---

## MJ相关

## sshport.sh

- 脚本说明: Linux一键更换默认端口

```bash
Usage:
| No.      | Bash Command                    
|----------|---------------------------------
| 1        | yum install wget
| 2        | wget -N --no-check-certificate https://github.com/O7Y0/script/raw/main/sshport.sh && chmod +x sshport.sh && bash sshport.sh
| 3        | 50000（或者任意你稀罕的）
| 4        | firewall:把修改的ssh端口添加到防火墙的放行端口,一定要执行这一步
| 5        | #如果防火墙使用的iptables（Centos 6），修改端口为50000
| 6        | iptables -I INPUT -p tcp --dport 50000 -j ACCEPT
| 7        | service iptables save
| 8        | service iptables restart
| 9        | #如果使用的是firewall（CentOS 7）
| 10       | firewall-cmd --zone=public --add-port=50000/tcp --permanent 
| 11       | firewall-cmd --reload
| 12       | reboot
| 13       | 使用修改后的端口登录
```

## bbr.sh|秋水逸冰

- 脚本说明: BBR加速

```bash
Usage:
| No.      | Bash Command                    
|----------|---------------------------------
| 1        | yum install wget
| 2        | wget --no-check-certificate -O /opt/bbr.sh https://github.com/O7Y0/script/raw/main/bbr.sh
| 3        | chmod 755 /opt/bbr.sh
| 4        | /opt/bbr.sh
| 5        | reboot
| 6        | uname -r 查看内核版本
| 7        | sysctl net.ipv4.tcp_available_congestion_control 查值,有查不查无所谓
| 8        | mount -o remount rw /  重启后磁盘变为只读情况需执行以下命令恢复
```
## bench-cn.sh|秋水逸冰

- 脚本说明: 自动测试 I/O 和上传下载速度剧本
```bash
Usage:
| No.      | Bash Command                    
|----------|---------------------------------
| 1        | yum install wget
| 2        | wget -N --no-check-certificate https://github.com/O7Y0/script/raw/main/bench-cn.sh && chmod +x bench-cn.sh && bash bench-cn.sh
```
## bench-abroad.sh|秋水逸冰

- 脚本说明: 自动测试 I/O 和上传下载速度剧本
```bash
Usage:
| No.      | Bash Command                    
|----------|---------------------------------
| 1        | yum install wget
| 2        | wget -N --no-check-certificate https://github.com/O7Y0/script/raw/main/bench-abroad.sh && chmod +x bench-abroad.sh && bash bench-abroad.sh
```

## memtester|FunctionClub

- 脚本说明: 检测VPS真实可分配内存
```bash
Usage:
| No.      | Bash Command                    
|----------|---------------------------------
| /        | CentOS / RHEL
| 1        | yum install wget
| 2        | yum groupinstall "Development Tools" -y
| 3        | wget https://raw.githubusercontent.com/O7Y0/script/raw/main/memtester.cpp
| 4        | gcc -l stdc++ memtester.cpp
| 5        | ./a.out
|          | 
| /        | Ubuntu / Debian：
| 1        | apt-get update
| 2        | apt-get install wget build-essential -y
| 3        | wget https://raw.githubusercontent.com/O7Y0/script/raw/main/memtester.cpp
| 4        | gcc -l stdc++ memtester.cpp
| 5        | ./a.out
```

## uPing|FunctionClub

- 脚本说明: 24小时监测VPS延迟
```bash
Usage:
| No.      | Bash Command                    
|----------|---------------------------------
| /        | CentOS / RHEL
| 1        | yum install screen wget python -y
| 2        | screen -S uping
| 3        | wget -N --no-check-certificate https://raw.githubusercontent.com/O7Y0/script/main/uping.py
| 4        | python uping.py
|          | 
| /        | Ubuntu / Debian：
| 1        | apt-get update
| 2        | apt-get install python wget screen -y
| 3        | screen -S uping
| 4        | wget -N --no-check-certificate https://raw.githubusercontent.com/O7Y0/script/main/uping.py
| 5        | python uping.py
```
