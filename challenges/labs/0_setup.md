* List the cloud provider you are using (AWS, GCE, Azure, other)
```
AWS
```
* List the Linux release you have chosen 
```
[root@ip-172-31-39-188 ~]# cat /etc/redhat-release 
CentOS Linux release 7.2.1511 (Core) 
```
* Show that the disk space on each node is at least 30 GB
```
[root@ip-172-31-39-188 ~]# fdisk -l  | grep '^Disk /dev/xvd*' && df -Ph /
Disk /dev/xvda: 42.9 GB, 42949672960 bytes, 83886080 sectors
Disk /dev/xvdb: 42.9 GB, 42949672960 bytes, 83886080 sectors
Filesystem               Size  Used Avail Use% Mounted on
/dev/mapper/centos-root   35G  995M   35G   3% /
```
```
[root@ip-172-31-47-91 ~]# fdisk -l  | grep '^Disk /dev/xvd*' && df -Ph /
Disk /dev/xvda: 42.9 GB, 42949672960 bytes, 83886080 sectors
Disk /dev/xvdb: 42.9 GB, 42949672960 bytes, 83886080 sectors
Filesystem               Size  Used Avail Use% Mounted on
/dev/mapper/centos-root   35G  995M   35G   3% /
```
```
[root@ip-172-31-45-185 ~]# fdisk -l  | grep '^Disk /dev/xvd*' && df -Ph /
Disk /dev/xvda: 42.9 GB, 42949672960 bytes, 83886080 sectors
Disk /dev/xvdb: 42.9 GB, 42949672960 bytes, 83886080 sectors
Filesystem               Size  Used Avail Use% Mounted on
/dev/mapper/centos-root   35G  995M   35G   3% /
```
```
[root@ip-172-31-36-117 ~]# fdisk -l  | grep '^Disk /dev/xvd*' && df -Ph /
Disk /dev/xvda: 42.9 GB, 42949672960 bytes, 83886080 sectors
Disk /dev/xvdb: 42.9 GB, 42949672960 bytes, 83886080 sectors
Filesystem               Size  Used Avail Use% Mounted on
/dev/mapper/centos-root   35G  995M   35G   3% /
```
```
[root@ip-172-31-44-109 ~]# fdisk -l  | grep '^Disk /dev/xvd*' && df -Ph /
Disk /dev/xvda: 42.9 GB, 42949672960 bytes, 83886080 sectors
Disk /dev/xvdb: 42.9 GB, 42949672960 bytes, 83886080 sectors
Filesystem               Size  Used Avail Use% Mounted on
/dev/mapper/centos-root   35G  995M   35G   3% /
```
* List the command and output for `yum repolist enabled` 
```
[root@ip-172-31-39-188 ~]# yum repolist enabled
Loaded plugins: fastestmirror
Repodata is over 2 weeks old. Install yum-cron? Or run: yum makecache fast
Determining fastest mirrors
 * base: ftp.heanet.ie
 * extras: ftp.heanet.ie
 * updates: ftp.heanet.ie
repo id                                                                                    repo name                                                                                    status
!base/7/x86_64                                                                             CentOS-7 - Base                                                                              9,007
!extras/7/x86_64                                                                           CentOS-7 - Extras                                                                              356
!updates/7/x86_64                                                                          CentOS-7 - Updates                                                                           2,002
repolist: 11,365

```
```
[root@ip-172-31-47-91 ~]# yum repolist enabled
Loaded plugins: fastestmirror
Repodata is over 2 weeks old. Install yum-cron? Or run: yum makecache fast
Determining fastest mirrors
 * base: ftp.heanet.ie
 * extras: ftp.heanet.ie
 * updates: ftp.heanet.ie
repo id                                                                                    repo name                                                                                    status
!base/7/x86_64                                                                             CentOS-7 - Base                                                                              9,007
!extras/7/x86_64                                                                           CentOS-7 - Extras                                                                              356
!updates/7/x86_64                                                                          CentOS-7 - Updates                                                                           2,002
repolist: 11,365
```
```
[root@ip-172-31-45-185 ~]# yum repolist enabled
Loaded plugins: fastestmirror
Repodata is over 2 weeks old. Install yum-cron? Or run: yum makecache fast
Determining fastest mirrors
 * base: ftp.heanet.ie
 * extras: ftp.heanet.ie
 * updates: ftp.heanet.ie
repo id                                                                                    repo name                                                                                    status
!base/7/x86_64                                                                             CentOS-7 - Base                                                                              9,007
!extras/7/x86_64                                                                           CentOS-7 - Extras                                                                              356
!updates/7/x86_64                                                                          CentOS-7 - Updates                                                                           2,002
repolist: 11,365
```
```
[root@ip-172-31-36-117 ~]# yum repolist enabled
Loaded plugins: fastestmirror
Repodata is over 2 weeks old. Install yum-cron? Or run: yum makecache fast
Determining fastest mirrors
 * base: ftp.heanet.ie
 * extras: ftp.heanet.ie
 * updates: ftp.heanet.ie
repo id                                                                                    repo name                                                                                    status
!base/7/x86_64                                                                             CentOS-7 - Base                                                                              9,007
!extras/7/x86_64                                                                           CentOS-7 - Extras                                                                              356
!updates/7/x86_64                                                                          CentOS-7 - Updates                                                                           2,002
repolist: 11,365
```
```
[root@ip-172-31-44-109 ~]# yum repolist enabled
Loaded plugins: fastestmirror
Repodata is over 2 weeks old. Install yum-cron? Or run: yum makecache fast
Determining fastest mirrors
 * base: ftp.heanet.ie
 * extras: ftp.heanet.ie
 * updates: ftp.heanet.ie
repo id                                                                                    repo name                                                                                    status
!base/7/x86_64                                                                             CentOS-7 - Base                                                                              9,007
!extras/7/x86_64                                                                           CentOS-7 - Extras                                                                              356
!updates/7/x86_64                                                                          CentOS-7 - Updates                                                                           2,002
repolist: 11,365
```
* Add the following Linux accounts to all nodes
    * User `ernest` with a UID of `2000`
    * User `siwicki` with a UID of `3000`
    * Create the group `usa` and add `ernest` to it
    * Create the group `emea` and add `siwicki` to it
* List the `/etc/passwd` entries for `ernest` and `siwicki` in your setup file
```
[root@ip-172-31-39-188 ~]# grep -E 'ernest|siwicki' /etc/passwd
ernest:x:2000:2000::/home/ernest:/bin/bash
siwicki:x:3000:3000::/home/siwicki:/bin/bash
```
```
[root@ip-172-31-47-91 ~]# grep -E 'ernest|siwicki' /etc/passwd
ernest:x:2000:2000::/home/ernest:/bin/bash
siwicki:x:3000:3000::/home/siwicki:/bin/bash
```
```
[root@ip-172-31-45-185 ~]# grep -E 'ernest|siwicki' /etc/passwd
ernest:x:2000:2000::/home/ernest:/bin/bash
siwicki:x:3000:3000::/home/siwicki:/bin/bash
```
```
[root@ip-172-31-36-117 ~]# grep -E 'ernest|siwicki' /etc/passwd
ernest:x:2000:2000::/home/ernest:/bin/bash
siwicki:x:3000:3000::/home/siwicki:/bin/bash
```
```
[root@ip-172-31-44-109 ~]# grep -E 'ernest|siwicki' /etc/passwd
ernest:x:2000:2000::/home/ernest:/bin/bash
siwicki:x:3000:3000::/home/siwicki:/bin/bash
```
* List the `/etc/group` entries for `usa` and `emea` in your setup file
```
[root@ip-172-31-39-188 ~]# grep -E 'usa|emea' /etc/group
usa:x:3001:ernest
emea:x:3002:siwicki
```
```
[root@ip-172-31-47-91 ~]# grep -E 'usa|emea' /etc/group
usa:x:3001:ernest
emea:x:3002:siwicki
```
```
[root@ip-172-31-45-185 ~]# grep -E 'usa|emea' /etc/group
usa:x:3001:ernest
emea:x:3002:siwicki
```
```
[root@ip-172-31-36-117 ~]# grep -E 'usa|emea' /etc/group
usa:x:3001:ernest
emea:x:3002:siwicki
```
```
[root@ip-172-31-44-109 ~]# grep -E 'usa|emea' /etc/group
usa:x:3001:ernest
emea:x:3002:siwicki
```
