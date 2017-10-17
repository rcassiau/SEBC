HDFS Lab: Test HDFS performance
* Create a 10 GB file using `teragen`
    * Set the number of mappers to four
    * Limit the block size to 32 MB 
    * Land the result under your user's home directory
    * Use the `time` command to report the job's duration
```
rcassiau@ip-172-31-43-15 ~]$ time hadoop jar /opt/cloudera/parcels/CDH-5.8.3-1.cdh5.8.3.p0.2/jars/hadoop-mapreduce-examples-2.6.0-cdh5.8.3.jar teragen -Ddfs.block.size=33554432 -Dmapreduce.job.maps=4 100000000 /user/rcassiau/teragen_10G
[...]
17/10/17 10:05:25 INFO mapreduce.Job:  map 100% reduce 0%
17/10/17 10:05:25 INFO mapreduce.Job: Job job_1508244387580_0008 completed successfully
17/10/17 10:05:25 INFO mapreduce.Job: Counters: 31
	File System Counters
		FILE: Number of bytes read=0
		FILE: Number of bytes written=500984
		FILE: Number of read operations=0
		FILE: Number of large read operations=0
		FILE: Number of write operations=0
		HDFS: Number of bytes read=344
		HDFS: Number of bytes written=10000000000
		HDFS: Number of read operations=16
		HDFS: Number of large read operations=0
		HDFS: Number of write operations=8
	Job Counters 
		Launched map tasks=4
		Other local map tasks=4
		Total time spent by all maps in occupied slots (ms)=542135
		Total time spent by all reduces in occupied slots (ms)=0
		Total time spent by all map tasks (ms)=542135
		Total vcore-seconds taken by all map tasks=542135
		Total megabyte-seconds taken by all map tasks=555146240
	Map-Reduce Framework
		Map input records=100000000
		Map output records=100000000
		Input split bytes=344
		Spilled Records=0
		Failed Shuffles=0
		Merged Map outputs=0
		GC time elapsed (ms)=1550
		CPU time spent (ms)=162020
		Physical memory (bytes) snapshot=879210496
		Virtual memory (bytes) snapshot=6309330944
		Total committed heap usage (bytes)=792723456
	org.apache.hadoop.examples.terasort.TeraGen$Counters
		CHECKSUM=214760662691937609
	File Input Format Counters 
		Bytes Read=0
	File Output Format Counters 
		Bytes Written=10000000000

real	2m28.534s
user	0m6.600s
sys	0m0.293s
```

* Run the `terasort` command on this file 
    * Use the `time` command to report the job's duration
    * Land the result under your user's home directory
```
[rcassiau@ip-172-31-43-15 ~]$ time hadoop jar /opt/cloudera/parcels/CDH-5.8.3-1.cdh5.8.3.p0.2/jars/hadoop-mapreduce-examples-2.6.0-cdh5.8.3.jar terasort /user/rcassiau/teragen_10G /user/rcassiau/terasort_10G
[...]
17/10/17 10:14:26 INFO mapreduce.Job: Job job_1508244387580_0009 completed successfully
17/10/17 10:14:26 INFO mapreduce.Job: Counters: 49
	File System Counters
		FILE: Number of bytes read=4444925230
		FILE: Number of bytes written=8826496413
		FILE: Number of read operations=0
		FILE: Number of large read operations=0
		FILE: Number of write operations=0
		HDFS: Number of bytes read=10000047400
		HDFS: Number of bytes written=10000000000
		HDFS: Number of read operations=918
		HDFS: Number of large read operations=0
		HDFS: Number of write operations=12
	Job Counters 
		Launched map tasks=300
		Launched reduce tasks=6
		Data-local map tasks=300
		Total time spent by all maps in occupied slots (ms)=3145475
		Total time spent by all reduces in occupied slots (ms)=655653
		Total time spent by all map tasks (ms)=3145475
		Total time spent by all reduce tasks (ms)=655653
		Total vcore-seconds taken by all map tasks=3145475
		Total vcore-seconds taken by all reduce tasks=655653
		Total megabyte-seconds taken by all map tasks=3220966400
		Total megabyte-seconds taken by all reduce tasks=671388672
	Map-Reduce Framework
		Map input records=100000000
		Map output records=100000000
		Map output bytes=10200000000
		Map output materialized bytes=4342784689
		Input split bytes=47400
		Combine input records=0
		Combine output records=0
		Reduce input groups=100000000
		Reduce shuffle bytes=4342784689
		Reduce input records=100000000
		Reduce output records=100000000
		Spilled Records=200000000
		Shuffled Maps =1800
		Failed Shuffles=0
		Merged Map outputs=1800
		GC time elapsed (ms)=42757
		CPU time spent (ms)=1501110
		Physical memory (bytes) snapshot=148303388672
		Virtual memory (bytes) snapshot=482274742272
		Total committed heap usage (bytes)=171949686784
	Shuffle Errors
		BAD_ID=0
		CONNECTION=0
		IO_ERROR=0
		WRONG_LENGTH=0
		WRONG_MAP=0
		WRONG_REDUCE=0
	File Input Format Counters 
		Bytes Read=10000000000
	File Output Format Counters 
		Bytes Written=10000000000
17/10/17 10:14:26 INFO terasort.TeraSort: done

real	6m52.048s
user	0m9.798s
sys	0m0.387s
```
