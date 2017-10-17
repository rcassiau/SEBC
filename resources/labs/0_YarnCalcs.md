1. Plug the hardware numbers for your cluster into the spreadsheet
2. Inspect the derived/default values. Adjust as necessary.
- Cloudera recommand to set only 8GB to the system so 10% allocated for the system are enough. I reduce CPU allocated to the system to 1, it should be enough.For me, all others values seems OK
3. What criteria affects workload factor? What does a value of 1, 2, or 4 signify?
Workload factor affects mapreduce.job.maps and mapreduce.job.reduces
Value 1 2 or 4 of workload factor signify the number of job running on a same workernode.
In my point of view, 1 permit to make intensive task with all the CPU, 2 permit to use in the same time the maximum of CPU and I/O, 4 permit to use all the performance of I/O disk
