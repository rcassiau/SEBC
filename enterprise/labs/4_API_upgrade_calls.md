* Use the API on the command line to:
  * Report the latest available version of the API
```
[root@ip-172-31-43-15 etc]# curl -u rcassiau:cloudera http://ec2-34-253-82-44.eu-west-1.compute.amazonaws.com:7180/api/version
v14
```
  * Report the CM version 
```
[root@ip-172-31-43-15 etc]# curl -u rcassiau:cloudera http://ec2-34-253-82-44.eu-west-1.compute.amazonaws.com:7180/api/v14/cm/version
{
  "version" : "5.9.3",
  "buildUser" : "jenkins",
  "buildTimestamp" : "20170627-1506",
  "gitHash" : "23506bb4e114dd460bdac64c57a672e6be631907",
  "snapshot" : false
}
```
  * List all CM users
```
[root@ip-172-31-43-15 etc]# curl -u rcassiau:cloudera http://ec2-34-253-82-44.eu-west-1.compute.amazonaws.com:7180/api/v14/users
{
  "items" : [ {
    "name" : "admin",
    "roles" : [ "ROLE_LIMITED" ]
  }, {
    "name" : "minotaur",
    "roles" : [ "ROLE_CONFIGURATOR" ]
  }, {
    "name" : "rcassiau",
    "roles" : [ "ROLE_ADMIN" ]
  } ]
}
```
  * Report the database server in use by CM
```
[root@ip-172-31-43-15 etc]# curl -u rcassiau:cloudera http://ec2-34-253-82-44.eu-west-1.compute.amazonaws.com:7180/api/v14/cm/scmDbInfo
{
  "scmDbType" : "MYSQL",
  "embeddedDbUsed" : false
}
```
