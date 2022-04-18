# 服务器搭建SSR+BBR翻墙教程

**系统要求：CentOS+、Debian7+、Ubuntu12+**

## 一、搭建服务器BBR

**首次需要安装wget**

```
yum install -y curl wget 2> /dev/null || apt install -y curl wget
```

**在服务器端运行以下代码：**

``` 
[root@instance-1 /]# yum -y install wget

[root@instance-1 /]# wget https://d.kxxzz.com/sh/tcp2020/tcp.sh

[root@instance-1 /]# chmod +x tcp.sh

[root@instance-1 /]# ./tcp.sh

//先安装内核，输入数字2，安装 BBR Plus内核，然后输入Y重启VPS，重启后继续

[root@instance-1 /]# ./tcp.sh

//输入数字13，安装BBR plus加速程序，安装完毕
```

## 二、安装SSR

**在服务器端运行以下代码：**

``` 
[root@instance-1 /]# yum -y install wget

[root@instance-1 /]# wget --no-check-certificate -O shadowsocks-all.sh https://raw.githubusercontent.com/teddysun/shadowsocks_install/master/shadowsocks-all.sh

[root@instance-1 /]# chmod +x shadowsocks-all.sh

[root@instance-1 /]# ./shadowsocks-all.sh

//配置选择
//2
//密码输入
//端口号输入
//2
//6
//6
```

### 启动脚本后面的参数含义，从左至右依次为：启动，停止，重启，查看状态

```
/etc/init.d/shadowsocks-r start | stop | restart | status
```

### 默认配置文件

```
/etc/shadowsocks-r/config.json
```

### 多账号配置

```json
{
        "server":"127.0.0.1",   #服务器的ip地址，不需要变更
        "local_address": "127.0.0.1",  #默认，不需要变更
        "local_port":1080,   #默认，不需要变更
        "port_password": {
                "6234": "jianmianli1",   #端口+密码
                "6235": "jianmianli2",
                "6236": "jianmianli3",
                "6237": "jianmianli4"
        },
        "timeout":300,
        "method":"aes-256-cfb",
        "fast_open": false
}
```

## 三、其他

**ShadowsocksR/SSR客户端[下载地址](https://tlanyan.me/shadowsockr-shadowsocksr-shadowsocksrr-clients/)**

**[国内IP测试地址](http://tool.chinaz.com/port/)**

**[海外IP测试地址](https://www.yougetsignal.com/tools/open-ports/)**

**一键脚本**

```
wget -O jcnfbox.sh https://raw.githubusercontent.com/Netflixxp/jcnf-box/main/jcnfbox.sh && chmod +x jcnfbox.sh && clear && ./jcnfbox.sh
```

