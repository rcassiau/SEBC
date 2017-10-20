* Add the following to `3_cm.md`:
    * Command and output for `hdfs dfs -ls /user`
```
[hdfs@ip-172-31-47-91 ~]$ hdfs dfs -ls /user
Found 3 items
drwxr-xr-x   - ernest  ernest           0 2017-10-20 05:29 /user/ernest
drwxrwxrwx   - mapred  hadoop           0 2017-10-20 05:29 /user/history
drwxr-xr-x   - siwicki siwicki          0 2017-10-20 05:29 /user/siwicki
```
    * The output from the CM API call `../api/v14/hosts` 
```
[root@ip-172-31-39-188 ~]# curl -u admin:admin 'http://ip-172-31-47-91.eu-west-1.compute.internal:7180/api/v14/hosts'
{
  "items" : [ {
    "hostId" : "0fc3d6fe-a661-4510-956e-01a98d2f9a28",
    "ipAddress" : "172.31.36.117",
    "hostname" : "ip-172-31-36-117.eu-west-1.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-47-91.eu-west-1.compute.internal:7180/cmf/hostRedirect/0fc3d6fe-a661-4510-956e-01a98d2f9a28",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 2,
    "totalPhysMemBytes" : 15332438016
  }, {
    "hostId" : "bfb3bfc4-3905-4dfe-9225-3003b475659d",
    "ipAddress" : "172.31.39.188",
    "hostname" : "ip-172-31-39-188.eu-west-1.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-47-91.eu-west-1.compute.internal:7180/cmf/hostRedirect/bfb3bfc4-3905-4dfe-9225-3003b475659d",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 2,
    "totalPhysMemBytes" : 15332438016
  }, {
    "hostId" : "7e1ad49f-6461-4ed9-bc5f-31467093edfe",
    "ipAddress" : "172.31.44.109",
    "hostname" : "ip-172-31-44-109.eu-west-1.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-47-91.eu-west-1.compute.internal:7180/cmf/hostRedirect/7e1ad49f-6461-4ed9-bc5f-31467093edfe",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 2,
    "totalPhysMemBytes" : 15332438016
  }, {
    "hostId" : "694db449-47ff-45f4-a982-7c062a1524cc",
    "ipAddress" : "172.31.45.185",
    "hostname" : "ip-172-31-45-185.eu-west-1.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-47-91.eu-west-1.compute.internal:7180/cmf/hostRedirect/694db449-47ff-45f4-a982-7c062a1524cc",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 2,
    "totalPhysMemBytes" : 15332438016
  }, {
    "hostId" : "i-03d396e32a29d9af7",
    "ipAddress" : "172.31.47.91",
    "hostname" : "ip-172-31-47-91.eu-west-1.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-47-91.eu-west-1.compute.internal:7180/cmf/hostRedirect/i-03d396e32a29d9af7",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 2,
    "totalPhysMemBytes" : 15332438016
  } ]
}
```
