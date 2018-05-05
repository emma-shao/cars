###centos开启nginx服务

sudo systemctl start nginx

###允许端口可以被访问

sudo firewall-cmd --permanent --zone=public --add-service=http
sudo firewall-cmd --reload

###系统启动时自动开启nginx

sudo systemctl enable nginx

###查看服务器的ip地址

ip addr

###查看对外访问地址
ip addr show eth0 | grep inet | awk '{ print $2; }' | sed 's/\/.*$//'

###配置web目录
>默认目录 /usr/share/nginx/html
>默认配置文件 /etc/nginx/conf.d/default.conf
>默认配置目录 /etc/nginx/conf.d 后缀为.conf会自动加载进来

###防火墙开启批量端口命令

firewall-cmd --permanent --zone=public --add-port=100-500/tcp
firewall-cmd --permanent --zone=public --add-port=100-500/udp
firewall-cmd --reload

###shadowsocks wiki地址
https://github.com/shadowsocks/shadowsocks/wiki/Shadowsocks-%E4%BD%BF%E7%94%A8%E8%AF%B4%E6%98%8E

###关闭shadowsocks服务

sudo ssserver -d stop

###检查日志

sudo less /var/log/shadowsocks.log
