```
[ernest@ip-172-31-39-188 ~]$ time hadoop jar /opt/cloudera/parcels/CDH-5.9.3-1.cdh5.9.3.p0.4/jars/hadoop-mapreduce-examples-2.6.0-cdh5.9.3.jar terasort /user/ernest/tgen512 /user/ernest/tsort512
17/10/20 06:02:53 INFO terasort.TeraSort: starting
17/10/20 06:02:54 INFO hdfs.DFSClient: Created token for ernest: HDFS_DELEGATION_TOKEN owner=ernest@RCASSIAU.CO.UK, renewer=yarn, realUser=, issueDate=1508493774890, maxDate=1509098574890, sequenceNumber=1, masterKeyId=2 on 172.31.39.188:8020
17/10/20 06:02:54 INFO security.TokenCache: Got dt for hdfs://ip-172-31-39-188.eu-west-1.compute.internal:8020; Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.39.188:8020, Ident: (token for ernest: HDFS_DELEGATION_TOKEN owner=ernest@RCASSIAU.CO.UK, renewer=yarn, realUser=, issueDate=1508493774890, maxDate=1509098574890, sequenceNumber=1, masterKeyId=2)
17/10/20 06:02:55 INFO input.FileInputFormat: Total input paths to process : 2
Spent 359ms computing base-splits.
Spent 4ms computing TeraScheduler splits.
Computing input splits took 363ms
Sampling 10 splits of 154
Making 6 from 100000 sampled records
Computing parititions took 891ms
Spent 1256ms computing partitions.
17/10/20 06:02:56 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-39-188.eu-west-1.compute.internal/172.31.39.188:8032
17/10/20 06:02:56 INFO mapreduce.JobSubmitter: number of splits:154
17/10/20 06:02:57 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1508493661574_0001
17/10/20 06:02:57 INFO mapreduce.JobSubmitter: Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.39.188:8020, Ident: (token for ernest: HDFS_DELEGATION_TOKEN owner=ernest@RCASSIAU.CO.UK, renewer=yarn, realUser=, issueDate=1508493774890, maxDate=1509098574890, sequenceNumber=1, masterKeyId=2)
17/10/20 06:02:58 INFO impl.YarnClientImpl: Submitted application application_1508493661574_0001
17/10/20 06:02:58 INFO mapreduce.Job: The url to track the job: http://ip-172-31-39-188.eu-west-1.compute.internal:8088/proxy/application_1508493661574_0001/
17/10/20 06:02:58 INFO mapreduce.Job: Running job: job_1508493661574_0001
17/10/20 06:03:07 INFO mapreduce.Job: Job job_1508493661574_0001 running in uber mode : false
17/10/20 06:03:07 INFO mapreduce.Job:  map 0% reduce 0%
17/10/20 06:03:18 INFO mapreduce.Job:  map 1% reduce 0%
17/10/20 06:03:19 INFO mapreduce.Job:  map 2% reduce 0%
17/10/20 06:03:23 INFO mapreduce.Job:  map 3% reduce 0%
17/10/20 06:03:24 INFO mapreduce.Job:  map 4% reduce 0%
17/10/20 06:03:26 INFO mapreduce.Job:  map 5% reduce 0%
17/10/20 06:03:27 INFO mapreduce.Job:  map 7% reduce 0%
17/10/20 06:03:28 INFO mapreduce.Job:  map 8% reduce 0%
17/10/20 06:03:33 INFO mapreduce.Job:  map 10% reduce 0%
17/10/20 06:03:35 INFO mapreduce.Job:  map 11% reduce 0%
17/10/20 06:03:37 INFO mapreduce.Job:  map 12% reduce 0%
17/10/20 06:03:40 INFO mapreduce.Job:  map 15% reduce 0%
17/10/20 06:03:44 INFO mapreduce.Job:  map 17% reduce 0%
17/10/20 06:03:45 INFO mapreduce.Job:  map 18% reduce 0%
17/10/20 06:03:48 INFO mapreduce.Job:  map 19% reduce 0%
17/10/20 06:03:52 INFO mapreduce.Job:  map 20% reduce 0%
17/10/20 06:03:53 INFO mapreduce.Job:  map 24% reduce 0%
17/10/20 06:03:55 INFO mapreduce.Job:  map 25% reduce 0%
17/10/20 06:04:00 INFO mapreduce.Job:  map 26% reduce 0%
17/10/20 06:04:02 INFO mapreduce.Job:  map 27% reduce 0%
17/10/20 06:04:03 INFO mapreduce.Job:  map 28% reduce 0%
17/10/20 06:04:04 INFO mapreduce.Job:  map 29% reduce 0%
17/10/20 06:04:05 INFO mapreduce.Job:  map 31% reduce 0%
17/10/20 06:04:06 INFO mapreduce.Job:  map 32% reduce 0%
17/10/20 06:04:11 INFO mapreduce.Job:  map 34% reduce 0%
17/10/20 06:04:13 INFO mapreduce.Job:  map 35% reduce 0%
17/10/20 06:04:14 INFO mapreduce.Job:  map 36% reduce 0%
17/10/20 06:04:17 INFO mapreduce.Job:  map 39% reduce 0%
17/10/20 06:04:20 INFO mapreduce.Job:  map 40% reduce 0%
17/10/20 06:04:22 INFO mapreduce.Job:  map 41% reduce 0%
17/10/20 06:04:23 INFO mapreduce.Job:  map 42% reduce 0%
17/10/20 06:04:26 INFO mapreduce.Job:  map 43% reduce 0%
17/10/20 06:04:30 INFO mapreduce.Job:  map 46% reduce 0%
17/10/20 06:04:31 INFO mapreduce.Job:  map 48% reduce 0%
17/10/20 06:04:33 INFO mapreduce.Job:  map 49% reduce 0%
17/10/20 06:04:38 INFO mapreduce.Job:  map 50% reduce 0%
17/10/20 06:04:40 INFO mapreduce.Job:  map 51% reduce 0%
17/10/20 06:04:41 INFO mapreduce.Job:  map 53% reduce 0%
17/10/20 06:04:42 INFO mapreduce.Job:  map 55% reduce 0%
17/10/20 06:04:43 INFO mapreduce.Job:  map 56% reduce 0%
17/10/20 06:04:50 INFO mapreduce.Job:  map 59% reduce 0%
17/10/20 06:04:51 INFO mapreduce.Job:  map 60% reduce 0%
17/10/20 06:04:53 INFO mapreduce.Job:  map 62% reduce 0%
17/10/20 06:04:54 INFO mapreduce.Job:  map 63% reduce 0%
17/10/20 06:04:58 INFO mapreduce.Job:  map 64% reduce 0%
17/10/20 06:05:00 INFO mapreduce.Job:  map 66% reduce 0%
17/10/20 06:05:02 INFO mapreduce.Job:  map 68% reduce 0%
17/10/20 06:05:04 INFO mapreduce.Job:  map 69% reduce 0%
17/10/20 06:05:07 INFO mapreduce.Job:  map 70% reduce 0%
17/10/20 06:05:10 INFO mapreduce.Job:  map 72% reduce 0%
17/10/20 06:05:12 INFO mapreduce.Job:  map 73% reduce 0%
17/10/20 06:05:13 INFO mapreduce.Job:  map 74% reduce 0%
17/10/20 06:05:15 INFO mapreduce.Job:  map 75% reduce 0%
17/10/20 06:05:17 INFO mapreduce.Job:  map 76% reduce 0%
17/10/20 06:05:18 INFO mapreduce.Job:  map 77% reduce 0%
17/10/20 06:05:19 INFO mapreduce.Job:  map 79% reduce 0%
17/10/20 06:05:20 INFO mapreduce.Job:  map 80% reduce 0%
17/10/20 06:05:23 INFO mapreduce.Job:  map 81% reduce 0%
17/10/20 06:05:28 INFO mapreduce.Job:  map 84% reduce 0%
17/10/20 06:05:29 INFO mapreduce.Job:  map 85% reduce 0%
17/10/20 06:05:30 INFO mapreduce.Job:  map 86% reduce 0%
17/10/20 06:05:32 INFO mapreduce.Job:  map 87% reduce 0%
17/10/20 06:05:35 INFO mapreduce.Job:  map 88% reduce 0%
17/10/20 06:05:38 INFO mapreduce.Job:  map 90% reduce 0%
17/10/20 06:05:40 INFO mapreduce.Job:  map 90% reduce 7%
17/10/20 06:05:42 INFO mapreduce.Job:  map 90% reduce 13%
17/10/20 06:05:43 INFO mapreduce.Job:  map 90% reduce 20%
17/10/20 06:05:45 INFO mapreduce.Job:  map 91% reduce 22%
17/10/20 06:05:46 INFO mapreduce.Job:  map 91% reduce 23%
17/10/20 06:05:47 INFO mapreduce.Job:  map 92% reduce 23%
17/10/20 06:05:48 INFO mapreduce.Job:  map 93% reduce 25%
17/10/20 06:05:49 INFO mapreduce.Job:  map 93% reduce 26%
17/10/20 06:05:50 INFO mapreduce.Job:  map 94% reduce 26%
17/10/20 06:05:55 INFO mapreduce.Job:  map 95% reduce 26%
17/10/20 06:05:57 INFO mapreduce.Job:  map 97% reduce 26%
17/10/20 06:05:59 INFO mapreduce.Job:  map 97% reduce 27%
17/10/20 06:06:01 INFO mapreduce.Job:  map 98% reduce 27%
17/10/20 06:06:02 INFO mapreduce.Job:  map 99% reduce 27%
17/10/20 06:06:05 INFO mapreduce.Job:  map 100% reduce 28%
17/10/20 06:06:07 INFO mapreduce.Job:  map 100% reduce 44%
17/10/20 06:06:08 INFO mapreduce.Job:  map 100% reduce 55%
17/10/20 06:06:10 INFO mapreduce.Job:  map 100% reduce 57%
17/10/20 06:06:11 INFO mapreduce.Job:  map 100% reduce 65%
17/10/20 06:06:13 INFO mapreduce.Job:  map 100% reduce 67%
17/10/20 06:06:14 INFO mapreduce.Job:  map 100% reduce 76%
17/10/20 06:06:16 INFO mapreduce.Job:  map 100% reduce 79%
17/10/20 06:06:17 INFO mapreduce.Job:  map 100% reduce 83%
17/10/20 06:06:19 INFO mapreduce.Job:  map 100% reduce 84%
17/10/20 06:06:20 INFO mapreduce.Job:  map 100% reduce 89%
17/10/20 06:06:22 INFO mapreduce.Job:  map 100% reduce 90%
17/10/20 06:06:23 INFO mapreduce.Job:  map 100% reduce 94%
17/10/20 06:06:24 INFO mapreduce.Job:  map 100% reduce 95%
17/10/20 06:06:25 INFO mapreduce.Job:  map 100% reduce 96%
17/10/20 06:06:26 INFO mapreduce.Job:  map 100% reduce 100%
17/10/20 06:06:27 INFO mapreduce.Job: Job job_1508493661574_0001 completed successfully
17/10/20 06:06:27 INFO mapreduce.Job: Counters: 49
	File System Counters
		FILE: Number of bytes read=2270863632
		FILE: Number of bytes written=4514422193
		FILE: Number of read operations=0
		FILE: Number of large read operations=0
		FILE: Number of write operations=0
		HDFS: Number of bytes read=5120023562
		HDFS: Number of bytes written=5120000000
		HDFS: Number of read operations=480
		HDFS: Number of large read operations=0
		HDFS: Number of write operations=12
	Job Counters 
		Launched map tasks=154
		Launched reduce tasks=6
		Data-local map tasks=154
		Total time spent by all maps in occupied slots (ms)=1376497
		Total time spent by all reduces in occupied slots (ms)=302123
		Total time spent by all map tasks (ms)=1376497
		Total time spent by all reduce tasks (ms)=302123
		Total vcore-seconds taken by all map tasks=1376497
		Total vcore-seconds taken by all reduce tasks=302123
		Total megabyte-seconds taken by all map tasks=1409532928
		Total megabyte-seconds taken by all reduce tasks=309373952
	Map-Reduce Framework
		Map input records=51200000
		Map output records=51200000
		Map output bytes=5222400000
		Map output materialized bytes=2223429323
		Input split bytes=23562
		Combine input records=0
		Combine output records=0
		Reduce input groups=51200000
		Reduce shuffle bytes=2223429323
		Reduce input records=51200000
		Reduce output records=51200000
		Spilled Records=102400000
		Shuffled Maps =924
		Failed Shuffles=0
		Merged Map outputs=924
		GC time elapsed (ms)=36204
		CPU time spent (ms)=833570
		Physical memory (bytes) snapshot=79226880000
		Virtual memory (bytes) snapshot=445559390208
		Total committed heap usage (bytes)=83626557440
	Shuffle Errors
		BAD_ID=0
		CONNECTION=0
		IO_ERROR=0
		WRONG_LENGTH=0
		WRONG_MAP=0
		WRONG_REDUCE=0
	File Input Format Counters 
		Bytes Read=5120000000
	File Output Format Counters 
		Bytes Written=5120000000
17/10/20 06:06:27 INFO terasort.TeraSort: done

real	3m34.942s
user	0m10.735s
sys	0m0.470s
```
