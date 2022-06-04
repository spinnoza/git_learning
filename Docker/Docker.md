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









# 3.Docker 原理解析

进入正在运行的容器的shell

~~~ shell
# docker exec -it 99da4c4dc7bc bash
~~~



# 4.Docker 实际的使用学习

查找镜像,拉取镜像

~~~ shell
# docker search centos
# docker pull 软件:版本号

# docker pull centos

~~~





 查看docker 的基本信息

~~~ shell
# docker info
~~~



查看docker 的安装路径

~~~ shell
# docker info | grep Root
 Docker Root Dir: /var/lib/docker
~~~



运行容器

~~~ shell
# -it 开启一个交互式的终端 -rm 退出容器时删除该容器
# docker run -it --rm centos bash
~~~





查看镜像

~~~ shell
# docker image ls
~~~



只列出镜像的Id

~~~ shell
# docker images -q
~~~



查看docker 镜像的信息

~~~ shell
# docker image inspect 5d0da3dc9764
~~~



# 5.Docker 的容器管理

docker run 等于创建+启动



**注意:容器内的进程必须处于前台运行状态,否则容器就会直接退出,自己部署一个容器运行,命令不得后台运行,前台运行即可**



如果容器内,什么事也没有做,容器也会挂掉,容器内,必须有一个进程在前台运行



查看容器日志,动态

docker logs -f + 容器Id

docker logs 容器Id | tail -5



进入一个正在运行的容器空间内

~~~ shell
# docker exec -it 99da4c4dc7bc bash
~~~



查看容器信息

~~~ shell
# docker container inspect 99da4c4dc7bc
~~~



运行容器,绑定端口号

~~~ shell
# docker run -d --name leoNginx -p 80:80 nginx
~~~



查看容器端口转发情况

~~~ shell
# docker port 99da4c4dc7bc
~~~





提交容器

![image-20220604104433212](Docker.assets/image-20220604104433212.png)



 

















