HDFS Lab: Replicate to another cluster
* Choose a partner in class
	David Boyer
* Name a source directory after your GitHub handle
	/user/rcassiau
* Name a target directory after your partner's GitHub handle
	/user/dboyer-ibm
* Use `teragen` to create a 500 MB file
```
[hdfs@ip-172-31-43-15 root]$ yarn jar /opt/cloudera/parcels/CDH/lib/hadoop-mapreduce/hadoop-mapreduce-examples.jar teragen 5120000 /user/rcassiau/teragen_512M
17/10/17 07:52:22 INFO client.ConfiguredRMFailoverProxyProvider: Failing over to rm41
17/10/17 07:52:22 INFO terasort.TeraSort: Generating 5120000 using 2
17/10/17 07:52:23 INFO mapreduce.JobSubmitter: number of splits:2
17/10/17 07:52:23 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1508238795812_0004
17/10/17 07:52:23 INFO impl.YarnClientImpl: Submitted application application_1508238795812_0004
17/10/17 07:52:23 INFO mapreduce.Job: The url to track the job: http://ip-172-31-43-15.eu-west-1.compute.internal:8088/proxy/application_1508238795812_0004/
17/10/17 07:52:23 INFO mapreduce.Job: Running job: job_1508238795812_0004
17/10/17 07:52:29 INFO mapreduce.Job: Job job_1508238795812_0004 running in uber mode : false
17/10/17 07:52:29 INFO mapreduce.Job:  map 0% reduce 0%
17/10/17 07:52:39 INFO mapreduce.Job:  map 100% reduce 0%
17/10/17 07:52:39 INFO mapreduce.Job: Job job_1508238795812_0004 completed successfully
17/10/17 07:52:39 INFO mapreduce.Job: Counters: 31
	File System Counters
		FILE: Number of bytes read=0
		FILE: Number of bytes written=250444
		FILE: Number of read operations=0
		FILE: Number of large read operations=0
		FILE: Number of write operations=0
		HDFS: Number of bytes read=167
		HDFS: Number of bytes written=512000000
		HDFS: Number of read operations=8
		HDFS: Number of large read operations=0
		HDFS: Number of write operations=4
	Job Counters 
		Launched map tasks=2
		Other local map tasks=2
		Total time spent by all maps in occupied slots (ms)=14894
		Total time spent by all reduces in occupied slots (ms)=0
		Total time spent by all map tasks (ms)=14894
		Total vcore-seconds taken by all map tasks=14894
		Total megabyte-seconds taken by all map tasks=15251456
	Map-Reduce Framework
		Map input records=5120000
		Map output records=5120000
		Input split bytes=167
		Spilled Records=0
		Failed Shuffles=0
		Merged Map outputs=0
		GC time elapsed (ms)=151
		CPU time spent (ms)=14530
		Physical memory (bytes) snapshot=739516416
		Virtual memory (bytes) snapshot=3165339648
		Total committed heap usage (bytes)=859308032
	org.apache.hadoop.examples.terasort.TeraGen$Counters
		CHECKSUM=10993942703914404
	File Input Format Counters 
		Bytes Read=0
	File Output Format Counters 
		Bytes Written=512000000
```

* Copy your partner's file to your target directory 
    * Let one partner use `distCp` on the command line
	David Boyer tried with distCp
    * Let the other use BDR
	I tried with BRD, but copy from David cluster to my cluster fail. It's probably due to AMAZON issue between both cluster. This operation was done locally through BDR and it's OK
* Browse the results 
    * Use `hdfs fsck <path> -files -blocks` on your source and target directories
	- from source directory

```
[hdfs@ip-172-31-43-15 root]$ hdfs fsck /user/rcassiau -files -blocks
Connecting to namenode via http://ip-172-31-43-15.eu-west-1.compute.internal:50070
FSCK started by hdfs (auth:SIMPLE) from /172.31.43.15 for path /user/rcassiau at Tue Oct 17 09:39:53 EDT 2017
/user/rcassiau <dir>
/user/rcassiau/teragen_512M <dir>
/user/rcassiau/teragen_512M/_SUCCESS 0 bytes, 0 block(s):  OK

/user/rcassiau/teragen_512M/part-m-00000 256000000 bytes, 2 block(s):  OK
0. BP-351076175-172.31.43.15-1508234408233:blk_1073742847_2023 len=134217728 Live_repl=3
1. BP-351076175-172.31.43.15-1508234408233:blk_1073742848_2024 len=121782272 Live_repl=3

/user/rcassiau/teragen_512M/part-m-00001 256000000 bytes, 2 block(s):  OK
0. BP-351076175-172.31.43.15-1508234408233:blk_1073742846_2022 len=134217728 Live_repl=3
1. BP-351076175-172.31.43.15-1508234408233:blk_1073742849_2025 len=121782272 Live_repl=3

Status: HEALTHY
 Total size:	512000000 B
 Total dirs:	2
 Total files:	3
 Total symlinks:		0
 Total blocks (validated):	4 (avg. block size 128000000 B)
 Minimally replicated blocks:	4 (100.0 %)
 Over-replicated blocks:	0 (0.0 %)
 Under-replicated blocks:	0 (0.0 %)
 Mis-replicated blocks:		0 (0.0 %)
 Default replication factor:	3
 Average block replication:	3.0
 Corrupt blocks:		0
 Missing replicas:		0 (0.0 %)
 Number of data-nodes:		3
 Number of racks:		1
FSCK ended at Tue Oct 17 09:39:53 EDT 2017 in 3 milliseconds


The filesystem under path '/user/rcassiau' is HEALTHY

```
	- from target directory 

```	
[hdfs@ip-172-31-43-15 root]$ hdfs fsck /user/dboyer-ibm -files -blocks
Connecting to namenode via http://ip-172-31-43-15.eu-west-1.compute.internal:50070
FSCK started by hdfs (auth:SIMPLE) from /172.31.43.15 for path /user/dboyer-ibm at Tue Oct 17 09:40:10 EDT 2017
/user/dboyer-ibm <dir>
/user/dboyer-ibm/aa <dir>
/user/dboyer-ibm/rcassiau <dir>
/user/dboyer-ibm/rcassiau/rcassiau <dir>
/user/dboyer-ibm/rcassiau/teragen_512M <dir>
/user/dboyer-ibm/rcassiau/teragen_512M/_SUCCESS 0 bytes, 0 block(s):  OK

/user/dboyer-ibm/rcassiau/teragen_512M/part-m-00000 256000000 bytes, 2 block(s):  OK
0. BP-351076175-172.31.43.15-1508234408233:blk_1073743251_2427 len=134217728 Live_repl=3
1. BP-351076175-172.31.43.15-1508234408233:blk_1073743253_2429 len=121782272 Live_repl=3

/user/dboyer-ibm/rcassiau/teragen_512M/part-m-00001 256000000 bytes, 2 block(s):  OK
0. BP-351076175-172.31.43.15-1508234408233:blk_1073743250_2426 len=134217728 Live_repl=3
1. BP-351076175-172.31.43.15-1508234408233:blk_1073743252_2428 len=121782272 Live_repl=3

/user/dboyer-ibm/test <dir>
Status: HEALTHY
 Total size:	512000000 B
 Total dirs:	6
 Total files:	3
 Total symlinks:		0
 Total blocks (validated):	4 (avg. block size 128000000 B)
 Minimally replicated blocks:	4 (100.0 %)
 Over-replicated blocks:	0 (0.0 %)
 Under-replicated blocks:	0 (0.0 %)
 Mis-replicated blocks:		0 (0.0 %)
 Default replication factor:	3
 Average block replication:	3.0
 Corrupt blocks:		0
 Missing replicas:		0 (0.0 %)
 Number of data-nodes:		3
 Number of racks:		1
FSCK ended at Tue Oct 17 09:40:10 EDT 2017 in 2 milliseconds


The filesystem under path '/user/dboyer-ibm' is HEALTHY
```

