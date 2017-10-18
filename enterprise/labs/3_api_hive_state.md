* Write `curl` statements that stop, start, and check the current state of your Hive service.
- Stop
```
[root@ip-172-31-43-15 ~]# curl -X POST -u rcassiau:cloudera 'http://ec2-34-253-82-44.eu-west-1.compute.amazonaws.com:7180/api/v12/clusters/rcassiau/services/hive/commands/stop'
{
  "id" : 830,
  "name" : "Stop",
  "startTime" : "2017-10-18T09:54:44.128Z",
  "active" : true,
  "serviceRef" : {
    "clusterName" : "cluster2",
    "serviceName" : "hive"
  }
}
```
- Start
```
[root@ip-172-31-43-15 ~]# curl -X POST -u rcassiau:cloudera 'http://ec2-34-253-82-44.eu-west-1.compute.amazonaws.com:7180/api/v12/clusters/rcassiau/services/hive/commands/start'
{
  "id" : 833,
  "name" : "Start",
  "startTime" : "2017-10-18T09:55:25.378Z",
  "active" : true,
  "serviceRef" : {
    "clusterName" : "cluster2",
    "serviceName" : "hive"
  }
}
```
- Status
```
[root@ip-172-31-43-15 ~]# curl -u rcassiau:cloudera http://ec2-34-253-82-44.eu-west-1.compute.amazonaws.com:7180/api/v12/clusters/rcassiau/services/hive
{
  "name" : "hive",
  "type" : "HIVE",
  "clusterRef" : {
    "clusterName" : "cluster2"
  },
  "serviceUrl" : "http://ip-172-31-43-15.eu-west-1.compute.internal:7180/cmf/serviceRedirect/hive",
  "roleInstancesUrl" : "http://ip-172-31-43-15.eu-west-1.compute.internal:7180/cmf/serviceRedirect/hive/instances",
  "serviceState" : "STARTED",
  "healthSummary" : "GOOD",
  "healthChecks" : [ {
    "name" : "HIVE_HIVEMETASTORES_HEALTHY",
    "summary" : "GOOD",
    "suppressed" : false
  }, {
    "name" : "HIVE_HIVESERVER2S_HEALTHY",
    "summary" : "GOOD",
    "suppressed" : false
  } ],
  "configStalenessStatus" : "FRESH",
  "clientConfigStalenessStatus" : "FRESH",
  "maintenanceMode" : false,
  "maintenanceOwners" : [ ],
  "displayName" : "Hive",
  "entityStatus" : "GOOD_HEALTH"
}
```
