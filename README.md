# 自搭vpn记录，之后换vps以便查看

## 1.境外服务器购买
    搬瓦工、Vultr（目前使用aws免费一年的服务器，需要信用卡以及电话验证，每个月出入15G）
## 2.服务器搭建Shadowsocks服务
    这里使用docker直接安装，比较方便
    
    安装docker
    yum install docker -y
    
    启动Docker
    service docker start（centos7 systemctl start docker）
    
    设置开机启动
    chkconfig docker on
    
    安装 Shadowsocks 的 VPN Docker 镜像
    docker pull oddrationale/docker-shadowsocks
    
    运行镜像
    docker run -d -p 2019:2019 oddrationale/docker-shadowsocks -s 0.0.0.0 -p 2019 -k 123456789 -m aes-256-cfb
    
    只需要修改端口和密码，其他默认即可
    -p 是端口：这里要前后一致，比如2019:2019 2019
    -k 后面设置你的 VPN 的密码，比如：123456789
    
    检查运行
    docker ps -a
## 3.下载Shadow Socks软件
    https://github.com/shadowsocks
## 4.连接
    打开软件填写服务器地址、端口号、密码、加密方式、代理端口
## 原文链接
    https://vkuajing.cc/vultr-vpn/
