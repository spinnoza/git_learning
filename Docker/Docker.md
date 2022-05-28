# Docker

# 1.安装Docker

配置yum源

~~~ shell
# wget -O /etc/yum.repos.d/epel.repo http://mirrors.aliyun.com/repo/epel-7.repo
# wget -O /etc/yum.repos.d/CentOS-Base.repo https://mirrors.aliyun.com/repo/Centos-7.repo
# yum clean all
# yum makecache
~~~

安装软件包

~~~ shell
# yum install -y bash-completion vim lrzsz wget expect net-tools nc nmap tree dos2unix htop iftop iotop unzip telnet sl psmisc nethogs glances bc ntpdate openldap-devel
~~~



开启linux内核流量转发

~~~ shell
cat <<EOF >  /etc/sysctl.d/.docker.conf
net.bridge.bridge-nf-call-ip6tables = 1
net.bridge.bridge-nf-call-iptables = 1
net.ipv4.conf.default.rp_filter = 0
net.ipv4.conf.all.rp_filter = 0
net.ipv4.ip_forward=1
EOF

# modprobe br_netfilter
# sysctl -p /etc/sysctl.d/.docker.conf
~~~

配置Docker网络源

~~~ shell
# curl -o /etc/yum.repos.d/docker-ce.repo http://mirrors.aliyun.com/docker-ce/linux/centos/docker-ce.repo
# curl -o /etc/yum.repos.d/Centos-7.repo http://mirrors.aliyun.com/repo/Centos-7.repo
# yum clean all && yum makecache
~~~



安装Docker

~~~ shell
# yum install docker-ce-20.10.6 -y
~~~



配置Docker 国内镜像

~~~ shell
# vim /etc/docker/daemon.json
{
  "registry-mirrors":["https://pee6w651.mirror.aliyuncs.com"]
}
~~~

加载配置，重启Docker

~~~ shell
# systemctl daemon-reload
# systemctl enable docker
# systemctl restart docker
~~~



查看Docker 版本

~~~ shell
# docker version
~~~



# 2.快速上手Docker

拉取nginx镜像,查看镜像,运行nginx

~~~ shell
# docker pull nginx
# docker image ls
# docker run -d -p 80:80 nginx
~~~

