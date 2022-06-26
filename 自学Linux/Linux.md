# Linux

## 1.常见问题

[**CentOS7 Failed to start LSB: Bring up/down解决方法**](https://blog.51cto.com/addam/1839518)

## 2.命令总结

1. 查看用户id

~~~ shell
# id -u
~~~



2.查看当前在哪个终端

~~~ shell
# tty
~~~



3.查看谁在登录

~~~ shell
# who
--当前人的登录信息
# who am i
~~~



4.谁在登录，在干什么

~~~ shell
# w
~~~



5.查看后台运行的一些程序

~~~ shell
# ps aux
~~~



6.查看当前Shell

~~~ shell
# echo $SHELL
~~~



7.查看当前系统支持的shell

~~~ shell
# cat /etc/shells
~~~



8.显示主机名

~~~ shell
# hostname
~~~



9.临时修改设置主机名

注意：主机名不要使用下划线

~~~ shell
# hostname zhangsan
~~~



10.查看存放主机名的文件

~~~ shell
# cat /etc/hostname
~~~



11.永久修改主机名

~~~ shell
# hostnamectl set-hostname lisi
~~~



12.查看当前提示符的格式

~~~shell
# echo $PS1
~~~



13.显示所有的内部命令

~~~ shell
#help
~~~



14.查看一个命令是内部命令还是外部命令

~~~ shell
#type who
#type -a echo
~~~



15.查看存放外部命令的路径

~~~ shell
[21:46:24 root@leohome ~]#echo $PATH
/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/root/bin
~~~



16.查看被系统缓存的外部命令

~~~ shell
#hash
~~~



17.显示外部命令的磁盘路径

~~~shell
[08:43:29 root@leohome ~]#which ping
/usr/bin/ping
~~~



18.显示外部命令的磁盘路径和相应帮助文档的路径

~~~ shell
[08:46:17 root@leohome ~]#whereis ping
ping: /usr/bin/ping /usr/share/man/man8/ping.8.gz
~~~



























