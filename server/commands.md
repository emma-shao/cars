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