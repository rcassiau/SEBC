* Install a MySQL 5.5.x server on the node you listed first
    * Use the YUM repository available at `dev.mysql.com`
    * Copy `/etc/yum.repos.d/mysql-community.repo` to `challenges/labs/1_mysql-community.repo.md`
```
[root@ip-172-31-39-188 yum.repos.d]# rpm -qa | grep mysql-community-server
mysql-community-server-5.5.58-2.el7.x86_64
```
* On all cluster nodes
    * Install the MySQL client package and JDBC connector jar
```
[root@ip-172-31-39-188 yum.repos.d]# rpm -qa | grep -E 'mysql-community-client|mysql-connector'
mysql-community-client-5.5.58-2.el7.x86_64
mysql-connector-java-5.1.25-3.el7.noarch
```
```
[root@ip-172-31-47-91 yum.repos.d]#  rpm -qa | grep -E 'mysql-community-client|mysql-connector'
mysql-connector-java-5.1.25-3.el7.noarch
mysql-community-client-5.5.58-2.el7.x86_64
```
```
[root@ip-172-31-45-185 yum.repos.d]#  rpm -qa | grep -E 'mysql-community-client|mysql-connector'
mysql-connector-java-5.1.25-3.el7.noarch
mysql-community-client-5.5.58-2.el7.x86_64
```
```
[root@ip-172-31-36-117 yum.repos.d]#  rpm -qa | grep -E 'mysql-community-client|mysql-connector'
mysql-connector-java-5.1.25-3.el7.noarch
mysql-community-client-5.5.58-2.el7.x86_64
```
```
[root@ip-172-31-44-109 yum.repos.d]#  rpm -qa | grep -E 'mysql-community-client|mysql-connector'
mysql-connector-java-5.1.25-3.el7.noarch
mysql-community-client-5.5.58-2.el7.x86_64
```
* Start the `mysqld` service
```
[root@ip-172-31-39-188 yum.repos.d]# systemctl start mysqld
[root@ip-172-31-39-188 yum.repos.d]# systemctl enable mysqld
Created symlink from /etc/systemd/system/mysql.service to /usr/lib/systemd/system/mysqld.service.
Created symlink from /etc/systemd/system/multi-user.target.wants/mysqld.service to /usr/lib/systemd/system/mysqld.service.
[root@ip-172-31-39-188 ~]# systemctl status mysqld
● mysqld.service - MySQL Community Server
   Loaded: loaded (/usr/lib/systemd/system/mysqld.service; enabled; vendor preset: disabled)
   Active: active (running) since Fri 2017-10-20 04:18:32 EDT; 1min 49s ago
  Process: 11180 ExecStartPost=/usr/bin/mysql-systemd-start post (code=exited, status=0/SUCCESS)
  Process: 11164 ExecStartPre=/usr/bin/mysql-systemd-start pre (code=exited, status=0/SUCCESS)
 Main PID: 11179 (mysqld_safe)
   CGroup: /system.slice/mysqld.service
           ├─11179 /bin/sh /usr/bin/mysqld_safe --basedir=/usr
           └─11570 /usr/sbin/mysqld --basedir=/usr --datadir=/var/lib/mysql --plugin-dir=/usr/lib64/mysql/plugin --log-error=/var/log/mysqld.log --pid-file=/var/run/mysqld/mysqld.pid
```
* Put the following in the file `challenges/labs/1_mysql.md`
    * The hostname of your MySQL node 
```
ip-172-31-39-188.eu-west-1.compute.internal
```
    * The command and output for `mysql --version`
```
[root@ip-172-31-39-188 ~]# mysql --version
mysql  Ver 14.14 Distrib 5.5.58, for Linux (x86_64) using readline 5.1
```
    * The command and output for listing MySQL databases 
```
mysql> show databases;
+-----------------------+
| Database              |
+-----------------------+
| information_schema    |
| #mysql50#backup-files |
| hive                  |
| hue                   |
| mysql                 |
| oozie                 |
| performance_schema    |
| rman                  |
| scm                   |
| sentry                |
+-----------------------+
10 rows in set (0.00 sec)
```
