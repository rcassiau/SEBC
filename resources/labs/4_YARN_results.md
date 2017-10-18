* Run this script from your edge node
    * Check it first: there are 1-2 things wrong with it
```
Create directory /results before execute the script and change the owner of the directory
```
* The parameters used and times of your slowest and fastest runs in `4_YARN_results.md`
	- Slowlest run
```
Teragen Configuration :
-Dmapreduce.job.maps=2
-Dmapreduce.map.memory.mb=2048
-Dmapreduce.map.java.opts.max.heap=1638

real	1m54.403s
user	0m6.101s
sys	0m0.273s

Terasort Configuration :
-Dmapreduce.job.maps=2
-Dmapreduce.job.reduces=1
-Dmapreduce.map.memory.mb=2048
-Dmapreduce.map.java.opts.max.heap=1638
-Dmapreduce.reduce.memory.mb=2048
-Dmapreduce.reduce.java.opts.max.heap=1638


real	3m44.795s
user	0m7.962s
sys	0m0.314s
```
	- Fastest run
```
Teragen Configuration :
-Dmapreduce.job.maps=8
-Dmapreduce.map.memory.mb=1024
-Dmapreduce.map.java.opts.max.heap=819

real	1m22.336s
user	0m5.707s
sys	0m0.302s

Terasort Configuration :
-Dmapreduce.job.maps=8
-Dmapreduce.job.reduces=8
-Dmapreduce.map.memory.mb=1024
-Dmapreduce.map.java.opts.max.heap=819
-Dmapreduce.reduce.memory.mb=1024
-Dmapreduce.reduce.java.opts.max.heap=819


real	1m49.466s
user	0m7.842s
sys	0m0.384s

```
