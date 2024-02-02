# 宁の集散🀄心
![GitHub](https://img.shields.io/github/license/mashape/apistatus.svg)
[![GitHub stars](https://img.shields.io/github/stars/DaMauu/script.svg?style=popout&label=Stars)](https://github.com/DaMauu/script/stargazers)
[![GitHub forks](https://img.shields.io/github/forks/DaMauu/script.svg?style=popout&label=Fork)](https://github.com/DaMauu/script/fork)
## 脚本索引
* [***MJ相关***](#代理相关)
  * [sshport.sh](https://github.com/DaMauu/script/blob/main/readme.md#sshportsh)
  * [bbr.sh](https://github.com/DaMauu/script/blob/main/readme.md#bbrsh%E7%A7%8B%E6%B0%B4%E9%80%B8%E5%86%B0)
  * [4-1bbr.sh](https://github.com/DaMauu/script/blob/main/readme.md#4-1bbrsh94ish)
  * [bench-cn.sh](https://github.com/DaMauu/script/blob/main/readme.md#bench-cnsh%E7%A7%8B%E6%B0%B4%E9%80%B8%E5%86%B0)
  * [bench-abroad.sh](https://github.com/DaMauu/script/blob/main/readme.md#bench-abroadsh%E7%A7%8B%E6%B0%B4%E9%80%B8%E5%86%B0)
  * [memtester.cpp](https://github.com/DaMauu/script/blob/main/readme.md#memtesterfunctionclub)
  * [uping.py](https://github.com/DaMauu/script/blob/main/readme.md#upingfunctionclub)
  * [superspeed.sh](https://github.com/DaMauu/script/blob/main/readme.md#superspeeduxh)
  * [virt-what](https://github.com/DaMauu/script/blob/main/readme.md#virt-whatrats)
---

## MJ相关

## sshport.sh

- 脚本说明: Linux一键更换默认端口

```bash
Usage:
| No.      | Bash Command                    
|----------|---------------------------------
| 1        | yum install wget
| 2        | wget -N --no-check-certificate https://github.com/DaMauu/script/raw/main/sshport.sh && chmod +x sshport.sh && bash sshport.sh
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
| 2        | wget --no-check-certificate -O /opt/bbr.sh https://github.com/DaMauu/script/raw/main/bbr.sh
| 3        | chmod 755 /opt/bbr.sh
| 4        | /opt/bbr.sh
| 5        | reboot
| 6        | uname -r 查看内核版本
| 7        | sysctl net.ipv4.tcp_available_congestion_control 查值,有查不查无所谓
| 8        | mount -o remount rw /  重启后磁盘变为只读情况需执行以下命令恢复
```

## 4-1bbr.sh|94ish

- 脚本说明: 4合1BBR加速

```bash
Usage:
| No.      | Bash Command                    
|----------|---------------------------------
| 1        | yum install wget
| 2        | wget -N --no-check-certificate "https://raw.githubusercontent.com/DaMauu/script/main/4-1bbr.sh" && chmod +x 4-1bbr.sh && ./4-1bbr.sh
| 3        | n 又可以出现询问卸载内核之类的
| 4        | y 重启
| 5        | ./4-1bbr.sh 重新开始使用后续操作
```
![4-1bbr.png](https://raw.githubusercontent.com/DaMauu/script/main/4-1bbr.png)
## bench-cn.sh|秋水逸冰

- 脚本说明: 自动测试 I/O 和上传下载速度剧本
```bash
Usage:
| No.      | Bash Command                    
|----------|---------------------------------
| 1        | yum install wget
| 2        | wget -N --no-check-certificate https://github.com/DaMauu/script/raw/main/bench-cn.sh && chmod +x bench-cn.sh && bash bench-cn.sh
```
## bench-abroad.sh|秋水逸冰

- 脚本说明: 自动测试 I/O 和上传下载速度剧本
```bash
Usage:
| No.      | Bash Command                    
|----------|---------------------------------
| 1        | yum install wget
| 2        | wget -N --no-check-certificate https://github.com/DaMauu/script/raw/main/bench-abroad.sh && chmod +x bench-abroad.sh && bash bench-abroad.sh
```
![bench-abroad.png](https://raw.githubusercontent.com/DaMauu/script/main/bench-abroad.png)
## memtester|FunctionClub

- 脚本说明: 检测VPS真实可分配内存
```bash
Usage:
| No.      | Bash Command                    
|----------|---------------------------------
| /        | CentOS / RHEL
| 1        | yum install wget
| 2        | yum groupinstall "Development Tools" -y
| 3        | wget https://raw.githubusercontent.com/DaMauu/script/raw/main/memtester.cpp
| 4        | gcc -l stdc++ memtester.cpp
| 5        | ./a.out
|          | 
| /        | Ubuntu / Debian：
| 1        | apt-get update
| 2        | apt-get install wget build-essential -y
| 3        | wget https://raw.githubusercontent.com/DaMauu/script/raw/main/memtester.cpp
| 4        | gcc -l stdc++ memtester.cpp
| 5        | ./a.out
```

## uPing|FunctionClub

- 脚本说明: 24小时监测VPS延迟
- 警告
目前正在测试阶段，请勿用于生产环境！
```bash
Usage:
| No.      | Bash Command                    
|----------|---------------------------------
| /        | CentOS / RHEL
| 1        | yum install screen wget python -y
| 2        | screen -S uping
| 3        | wget -N --no-check-certificate https://raw.githubusercontent.com/DaMauu/script/main/uping.py
| 4        | python uping.py
|          | 
| /        | Ubuntu / Debian：
| 1        | apt-get update
| 2        | apt-get install python wget screen -y
| 3        | screen -S uping
| 4        | wget -N --no-check-certificate https://raw.githubusercontent.com/DaMauu/script/main/uping.py
| 5        | python uping.py
```
![uping.png](https://raw.githubusercontent.com/DaMauu/script/main/uping.png)

## superspeed|uxh

- 脚本说明: 进行全国三大运营商speedtest测速节点测速
```bash
Usage:
| No.      | Bash Command                    
|----------|---------------------------------
| 1        | yum install wget
| 2        | wget -N --no-check-certificate https://github.com/DaMauu/script/raw/main/superspeed.sh && chmod +x superspeed.sh && bash superspeed.sh
```
![SuperSpeed.png](https://raw.githubusercontent.com/DaMauu/script/main/SuperSpeed.png)

## virt-what|Rat's

- 脚本说明: 使用virt-what判断VPS虚拟化技术
```bash
Usage:
| No.      | Bash Command                    
|----------|---------------------------------
| 1        | yum install wget
| 2        | wget https://github.com/DaMauu/script/releases/download/virt-what/virt-what-1.11.tar.gz
| 3        | tar zxf virt-what-1.11.tar.gz   #解压缩包
| 4        | cd virt-what-1.11               #进入目录
| 5        | ./configure                     #按默认设置
| 6        | make && make install            #编译并安装
| 7        | virt-what                       #查看
```
