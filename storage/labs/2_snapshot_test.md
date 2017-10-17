HDFS Lab: Test HDFS Snapshots
List the commands and output for each step below in `storage/labs/2_snapshot_test.md`.
* Create a `precious` directory in HDFS; copy the ZIP course file into it.
```
[hdfs@ip-172-31-43-15 ~]$ hdfs dfs -mkdir /precious
[hdfs@ip-172-31-43-15 ~]$ hdfs dfs -put /tmp/SEBC-master.zip /precious
[hdfs@ip-172-31-43-15 ~]$ hdfs dfs -ls /precious
Found 1 items
-rw-r--r--   3 hdfs supergroup     450893 2017-10-17 10:23 /precious/SEBC-master.zip
```
* Enable snapshots for `precious`
* Create a snapshot called `sebc-hdfs-test`
* Delete the directory
	- Unable to delete the directory :
```
[hdfs@ip-172-31-43-15 ~]$ hdfs dfs -rm -r -f -skipTrash /precious
rm: The directory /precious cannot be deleted since /precious is snapshottable and already has snapshots
```
* Delete the ZIP file
```
[hdfs@ip-172-31-43-15 ~]$ hdfs dfs -rm -skipTrash /precious/SEBC-master.zip
Deleted /precious/SEBC-master.zip
```
* Restore the deleted file 
```
[hdfs@ip-172-31-43-15 ~]$ hdfs dfs -ls /precious
Found 1 items
-rw-r--r--   3 hdfs supergroup     450893 2017-10-17 10:34 /precious/SEBC-master.zip
```
