1. Plug the hardware numbers for your cluster into the spreadsheet
2. Inspect the derived/default values. Adjust as necessary.
- Cloudera recommand to set only 8GB to the system so 10% allocated for the system are enough. I reduce CPU allocated to the system to 1, it should be enough.For me, all others values seems OK
3. What criteria affects workload factor? What does a value of 1, 2, or 4 signify?
Workload factor affects mapreduce.job.maps and mapreduce.job.reduces
