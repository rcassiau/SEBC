* What is ubertask optimization?
```
Whether to enable ubertask optimization, which runs "sufficiently small" jobs sequentially within a single JVM. "Small" is defined by the mapreduce.job.ubertask.maxmaps, mapreduce.job.ubertask.maxreduces, and mapreduce.job.ubertask.maxbytes settings.
```
* Where in CM is the Kerberos Security Realm value displayed?
```
Administration > Settings > Filter: Kerberos > Kerberos Security Realm : default_realm
or search directly in the right bar "Kerberos Security Realm"

```
* Which CDH service(s) host a property for enabling Kerberos authentication?
```
All of CDH services support kerberos authentification
```
* How do you upgrade the CM agents?
```
You can upgrade the CM agents through the wizard suggest into the Hosts tab : "Re-run Upgrade Wizard"
```
* Give the `tsquery` statement used to chart Hue's CPU utilization?
```
select cpu_system_rate + cpu_user_rate where category=ROLE and serviceName=hue
```
* Name all the roles that make up the Hive service
```
Hive Metastore Server
WebHCat Server
HiveServer2
Hive Gateway
```
* What steps must be completed before integrating Cloudera Manager with Kerberos?
```
When you want to Enable Kerberos for the cluster, the wizard hint us to check if theses following steps have been done :
- Set up a working KDC. Cloudera Manager supports MIT KDC and Active Directory.
- The KDC should be configured to have non-zero ticket lifetime and renewal lifetime. CDH will not work properly if tickets are not renewable.
- OpenLdap client libraries should be installed on the Cloudera Manager Server host if you want to use Active Directory. Also, Kerberos client libraries should be installed on ALL hosts.
- Cloudera Manager needs an account that has permissions to create other accounts in the KDC. 
```
