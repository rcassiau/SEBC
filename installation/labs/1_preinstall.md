- Check vm.swappiness on all your nodes
```
===> set swappiness to 1 on all hosts
sysctl vm.swappiness=1
===> set swappiness to 1 definitively on all hosts
echo vm.swappiness=1 >> /etc/sysctl.conf
[root@ip-172-31-43-15 ~]# sysctl vm.swappiness
vm.swappiness = 1
```
- Show the mount attributes of all volumes
```
[root@ip-172-31-43-15 ~]# mount
sysfs on /sys type sysfs (rw,nosuid,nodev,noexec,relatime,seclabel)
proc on /proc type proc (rw,nosuid,nodev,noexec,relatime)
devtmpfs on /dev type devtmpfs (rw,nosuid,seclabel,size=7607544k,nr_inodes=1901886,mode=755)
securityfs on /sys/kernel/security type securityfs (rw,nosuid,nodev,noexec,relatime)
tmpfs on /dev/shm type tmpfs (rw,nosuid,nodev,seclabel)
devpts on /dev/pts type devpts (rw,nosuid,noexec,relatime,seclabel,gid=5,mode=620,ptmxmode=000)
tmpfs on /run type tmpfs (rw,nosuid,nodev,seclabel,mode=755)
tmpfs on /sys/fs/cgroup type tmpfs (ro,nosuid,nodev,noexec,seclabel,mode=755)
cgroup on /sys/fs/cgroup/systemd type cgroup (rw,nosuid,nodev,noexec,relatime,xattr,release_agent=/usr/lib/systemd/systemd-cgroups-agent,name=systemd)
pstore on /sys/fs/pstore type pstore (rw,nosuid,nodev,noexec,relatime)
cgroup on /sys/fs/cgroup/memory type cgroup (rw,nosuid,nodev,noexec,relatime,memory)
cgroup on /sys/fs/cgroup/cpu,cpuacct type cgroup (rw,nosuid,nodev,noexec,relatime,cpuacct,cpu)
cgroup on /sys/fs/cgroup/devices type cgroup (rw,nosuid,nodev,noexec,relatime,devices)
cgroup on /sys/fs/cgroup/perf_event type cgroup (rw,nosuid,nodev,noexec,relatime,perf_event)
cgroup on /sys/fs/cgroup/blkio type cgroup (rw,nosuid,nodev,noexec,relatime,blkio)
cgroup on /sys/fs/cgroup/cpuset type cgroup (rw,nosuid,nodev,noexec,relatime,cpuset)
cgroup on /sys/fs/cgroup/hugetlb type cgroup (rw,nosuid,nodev,noexec,relatime,hugetlb)
cgroup on /sys/fs/cgroup/net_cls type cgroup (rw,nosuid,nodev,noexec,relatime,net_cls)
cgroup on /sys/fs/cgroup/freezer type cgroup (rw,nosuid,nodev,noexec,relatime,freezer)
configfs on /sys/kernel/config type configfs (rw,relatime)
/dev/mapper/centos-root on / type xfs (rw,relatime,seclabel,attr2,inode64,noquota)
selinuxfs on /sys/fs/selinux type selinuxfs (rw,relatime)
systemd-1 on /proc/sys/fs/binfmt_misc type autofs (rw,relatime,fd=24,pgrp=1,timeout=300,minproto=5,maxproto=5,direct)
debugfs on /sys/kernel/debug type debugfs (rw,relatime)
mqueue on /dev/mqueue type mqueue (rw,relatime,seclabel)
hugetlbfs on /dev/hugepages type hugetlbfs (rw,relatime,seclabel)
/dev/xvda1 on /boot type xfs (rw,relatime,seclabel,attr2,inode64,noquota)
tmpfs on /run/user/1000 type tmpfs (rw,nosuid,nodev,relatime,seclabel,size=1497312k,mode=700,uid=1000,gid=1000)
tmpfs on /run/user/0 type tmpfs (rw,nosuid,nodev,relatime,seclabel,size=1497312k,mode=700)
/dev/xvdb1 on /data type xfs (rw,noatime,seclabel,attr2,inode64,noquota)
```

- Show the reserve space of any non-root, ext-based volumes
```
All disk are mounted in xfs
```
- Disable transparent hugepage support
```
[root@ip-172-31-43-15 ~]# sysctl -a | grep hugepage
vm.hugepages_treat_as_movable = 0
vm.nr_hugepages = 0
vm.nr_hugepages_mempolicy = 0
vm.nr_overcommit_hugepages = 0
```
- List your network interface configuration
```
[root@ip-172-31-43-15 ~]# ip a
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN 
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
2: eth0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 9001 qdisc pfifo_fast state UP qlen 1000
    link/ether 0a:85:bc:82:6d:2e brd ff:ff:ff:ff:ff:ff
    inet 172.31.43.15/20 brd 172.31.47.255 scope global dynamic eth0
       valid_lft 3581sec preferred_lft 3581sec
```
- List forward and reverse host lookups using getent or nslookup
```
[root@ip-172-31-43-15 ~]# nslookup ec2-34-253-82-44.eu-west-1.compute.amazonaws.com
Server:		172.31.0.2
Address:	172.31.0.2#53

Non-authoritative answer:
Name:	ec2-34-253-82-44.eu-west-1.compute.amazonaws.com
Address: 172.31.43.15

[root@ip-172-31-43-15 ~]# nslookup ec2-34-240-32-191.eu-west-1.compute.amazonaws.com
Server:		172.31.0.2
Address:	172.31.0.2#53

Non-authoritative answer:
Name:	ec2-34-240-32-191.eu-west-1.compute.amazonaws.com
Address: 172.31.39.234

[root@ip-172-31-43-15 ~]# nslookup ec2-34-240-76-30.eu-west-1.compute.amazonaws.com
Server:		172.31.0.2
Address:	172.31.0.2#53

Non-authoritative answer:
Name:	ec2-34-240-76-30.eu-west-1.compute.amazonaws.com
Address: 172.31.46.129

[root@ip-172-31-43-15 ~]# nslookup ec2-34-249-58-174.eu-west-1.compute.amazonaws.com
Server:		172.31.0.2
Address:	172.31.0.2#53

Non-authoritative answer:
Name:	ec2-34-249-58-174.eu-west-1.compute.amazonaws.com
Address: 172.31.38.222

[root@ip-172-31-43-15 ~]# nslookup ec2-52-208-110-249.eu-west-1.compute.amazonaws.com
Server:		172.31.0.2
Address:	172.31.0.2#53

Non-authoritative answer:
Name:	ec2-52-208-110-249.eu-west-1.compute.amazonaws.com
Address: 172.31.41.242
```
- Verify the nscd service is running
```
[root@ip-172-31-43-15 ~]# systemctl status nscd
● nscd.service - Name Service Cache Daemon
   Loaded: loaded (/usr/lib/systemd/system/nscd.service; enabled; vendor preset: disabled)
   Active: active (running) since Mon 2017-10-16 09:46:38 EDT; 1s ago
  Process: 3878 ExecStop=/usr/sbin/nscd --shutdown (code=exited, status=0/SUCCESS)
  Process: 3886 ExecStart=/usr/sbin/nscd $NSCD_OPTIONS (code=exited, status=0/SUCCESS)
 Main PID: 3887 (nscd)
   CGroup: /system.slice/nscd.service
           └─3887 /usr/sbin/nscd
```
- Verify the ntpd service is running
```
root@ip-172-31-43-15 ~]# systemctl status ntpd
● ntpd.service - Network Time Service
   Loaded: loaded (/usr/lib/systemd/system/ntpd.service; enabled; vendor preset: disabled)
   Active: active (running) since Mon 2017-10-16 08:55:50 EDT; 51min ago
 Main PID: 2892 (ntpd)
   CGroup: /system.slice/ntpd.service
           └─2892 /usr/sbin/ntpd -u ntp:ntp -g
```
