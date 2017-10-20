* Install a supported version of Java 8 on all machines
* Assign yourself to the Issue and label it `started`
* Install Cloudera Manager on a different node from MySQL
* Configure the CM repo to install the 5.9 release
  * List the command and output of `ls /etc/yum.repos.d` in `challenges/labs/2_cm.md`
```
[root@ip-172-31-47-91 ~]# ls -l /etc/yum.repos.d/
total 40
-rw-r--r--. 1 root root 1664 Dec  9  2015 CentOS-Base.repo
-rw-r--r--. 1 root root 1309 Dec  9  2015 CentOS-CR.repo
-rw-r--r--. 1 root root  649 Dec  9  2015 CentOS-Debuginfo.repo
-rw-r--r--. 1 root root  290 Dec  9  2015 CentOS-fasttrack.repo
-rw-r--r--. 1 root root  630 Dec  9  2015 CentOS-Media.repo
-rw-r--r--. 1 root root 1331 Dec  9  2015 CentOS-Sources.repo
-rw-r--r--. 1 root root 1952 Dec  9  2015 CentOS-Vault.repo
-rw-r--r--. 1 root root  291 Oct 20 04:33 cloudera-manager.repo
-rw-r--r--. 1 root root 1838 Oct 20 03:50 mysql-community.repo
-rw-r--r--. 1 root root 1885 Apr 27 05:14 mysql-community-source.repo
```
* Configure Cloudera Manager
  * Use the `scm_prepare_database.sh` script to write your `db.properties` file 
    * List the full command line in `2_cm.md`
```
[root@ip-172-31-47-91 UnlimitedJCEPolicyJDK8]# /usr/share/cmf/schema/scm_prepare_database.sh -h ip-172-31-39-188 mysql scm scm scm
JAVA_HOME=/usr/java/jdk1.8.0_131
Verifying that we can write to /etc/cloudera-scm-server
Creating SCM configuration file in /etc/cloudera-scm-server
Executing:  /usr/java/jdk1.8.0_131/bin/java -cp /usr/share/java/mysql-connector-java.jar:/usr/share/java/oracle-connector-java.jar:/usr/share/cmf/schema/../lib/* com.cloudera.enterprise.dbutil.DbCommandExecutor /etc/cloudera-scm-server/db.properties com.cloudera.cmf.db.
[                          main] DbCommandExecutor              INFO  Successfully connected to database.
All done, your SCM database is configured correctly!
```
