* Put the following in the file `challenges/labs/4_teragen.md`
    * The full `teragen` command 
```
time hadoop jar /opt/cloudera/parcels/CDH-5.9.3-1.cdh5.9.3.p0.4/jars/hadoop-mapreduce-examples-2.6.0-cdh5.9.3.jar teragen -Ddfs.block.size=33554432 51200000 /user/ernest/tgen512
```
    * The output of the `time` command
```
real	2m42.987s
user	0m7.433s
sys	0m0.356s
```
    * The command and output of `hdfs dfs -ls /user/ernest/tgen512`
```
[ernest@ip-172-31-39-188 ~]$ hdfs dfs -ls /user/ernest/tgen512
Found 3 items
-rw-r--r--   3 ernest ernest          0 2017-10-20 05:48 /user/ernest/tgen512/_SUCCESS
-rw-r--r--   3 ernest ernest 2560000000 2017-10-20 05:48 /user/ernest/tgen512/part-m-00000
-rw-r--r--   3 ernest ernest 2560000000 2017-10-20 05:48 /user/ernest/tgen512/part-m-00001
```
    * Show how many blocks are associated with this directory
```
[ernest@ip-172-31-39-188 ~]$ hdfs fsck /user/ernest/tgen512  -blocks
Connecting to namenode via http://ip-172-31-39-188.eu-west-1.compute.internal:50070
FSCK started by ernest (auth:SIMPLE) from /172.31.39.188 for path /user/ernest/tgen512 at Fri Oct 20 05:51:17 EDT 2017
...Status: HEALTHY
 Total size:	5120000000 B
 Total dirs:	1
 Total files:	3
 Total symlinks:		0
 Total blocks (validated):	154 (avg. block size 33246753 B)
 Minimally replicated blocks:	154 (100.0 %)
 Over-replicated blocks:	0 (0.0 %)
 Under-replicated blocks:	0 (0.0 %)
 Mis-replicated blocks:		0 (0.0 %)
 Default replication factor:	3
 Average block replication:	3.0
 Corrupt blocks:		0
 Missing replicas:		0 (0.0 %)
 Number of data-nodes:		3
 Number of racks:		1
FSCK ended at Fri Oct 20 05:51:17 EDT 2017 in 2 milliseconds


The filesystem under path '/user/ernest/tgen512' is HEALTHY
```
