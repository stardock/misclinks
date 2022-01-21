# misclinks
My own notes  

How to clear memory cache in linux  
https://www.tecmint.com/clear-ram-memory-cache-buffer-and-swap-space-on-linux/  

Cloudflare从入门到放弃  
https://www.jianshu.com/p/7f38989ffa15  


使用 systemd 限制系统资源的使用  
https://www.ctolib.com/topics-136975.html  

Brook/iptables端口转发 一键管理脚本，支持DDNS-主机百科  
https://zhujiwiki.com/17239/  

port-forward: Go语言开发的端口转发工具 for port data forward  
https://gitee.com/tavenli/port-forward  


centos 允许非root用户监听特权端口  
特权端口=privileged port=1024 以下端口  
```  
useradd ssuser
cp -r shadowsocks /home/ssuser/
setcap CAP_NET_BIND_SERVICE=+eip  /usr/bin/python2.7
chmod 777 /etc/hosts.allow
chmod 777 /etc/hosts.deny
ll /etc/hosts*
cd /home/ssuser/shadowsocks
git reset --hard
git pull
git reset --hard
vi /etc/systemd/system/ssr.service
```  
https://peter-mao.blogspot.com/2016/04/centos-root.html  

CentOS 7不重启刷新磁盘列表  
```
ls /sys/class/scsi_host/
echo "- - -" > /sys/class/scsi_host/host0/scan
echo "- - -" > /sys/class/scsi_host/host1/scan
echo "- - -" > /sys/class/scsi_host/host2/scan
fdisk -l
```
https://www.cnblogs.com/zd520pyx1314/p/8532356.html  

centos 7 进单用户修改密码  
```
编辑修改两处：ro改为rw，在LANG=en_US.UFT-8后面添加 init=/bin/sh
按Ctrl+x 重启进入单用户，修改密码
touch /.autorelabel
exec /sbin/init
```  
https://blog.51cto.com/chaichuan/1983741  

lvm进阶  
先创建分区，然后创建pv,创建vg，最后再创建lv。之后可能需要格式化 mkfs.ext4 或者 resize2fs / xfs growfs  
partprobe 重新加载分区表  

单用户模式  
```
rd.break console=tty0
mount -s remount.tw /sysroot
chroot /sysroot
echo $SHELL
```

selinux模式  
```
ls -Z 查看文件的安全上下文
ps -U 查看进程的安全上下文
```
linux中的浏览器 lynx  
