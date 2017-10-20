```
[ernest@ip-172-31-39-188 ~]$ klist
Ticket cache: FILE:/tmp/krb5cc_2000
Default principal: ernest@RCASSIAU.CO.UK

Valid starting       Expires              Service principal
10/20/2017 06:11:24  10/21/2017 06:11:24  krbtgt/RCASSIAU.CO.UK@RCASSIAU.CO.UK
	renew until 10/27/2017 06:11:24


[ernest@ip-172-31-39-188 ~]$ beeline
Java HotSpot(TM) 64-Bit Server VM warning: ignoring option MaxPermSize=512M; support was removed in 8.0
Java HotSpot(TM) 64-Bit Server VM warning: ignoring option MaxPermSize=512M; support was removed in 8.0
Beeline version 1.1.0-cdh5.9.3 by Apache Hive
beeline> !connect jdbc:hive2://ip-172-31-47-91.eu-west-1.compute.internal:10000/default;principal=hive/ip-172-31-47-91.eu-west-1.compute.internal@RCASSIAU.CO.UK
scan complete in 3ms
0: jdbc:hive2://ip-172-31-47-91.eu-west-1.com> show tables;
INFO  : Compiling command(queryId=hive_20171020062222_6d309fe2-6ae3-4131-9675-b69317ff80e5): show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20171020062222_6d309fe2-6ae3-4131-9675-b69317ff80e5); Time taken: 0.047 seconds
INFO  : Executing command(queryId=hive_20171020062222_6d309fe2-6ae3-4131-9675-b69317ff80e5): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171020062222_6d309fe2-6ae3-4131-9675-b69317ff80e5); Time taken: 0.113 seconds
INFO  : OK

+------------+--+
|  tab_name  |
+------------+--+
| customers  |
| sample_07  |
| sample_08  |
| web_logs   |
+------------+--+
```
```
[siwicki@ip-172-31-39-188 ~]$ klist
Ticket cache: FILE:/tmp/krb5cc_3000
Default principal: siwicki@RCASSIAU.CO.UK

Valid starting       Expires              Service principal
10/20/2017 06:25:32  10/21/2017 06:25:32  krbtgt/RCASSIAU.CO.UK@RCASSIAU.CO.UK
	renew until 10/27/2017 06:25:32
[siwicki@ip-172-31-39-188 ~]$ beeline
Java HotSpot(TM) 64-Bit Server VM warning: ignoring option MaxPermSize=512M; support was removed in 8.0
Java HotSpot(TM) 64-Bit Server VM warning: ignoring option MaxPermSize=512M; support was removed in 8.0
Beeline version 1.1.0-cdh5.9.3 by Apache Hive
beeline> !connect jdbc:hive2://ip-172-31-47-91.eu-west-1.compute.internal:10000/default;principal=hive/ip-172-31-47-91.eu-west-1.compute.internal@RCASSIAU.CO.UK
scan complete in 2ms
Connecting to jdbc:hive2://ip-172-31-47-91.eu-west-1.compute.internal:10000/default;principal=hive/ip-172-31-47-91.eu-west-1.compute.internal@RCASSIAU.CO.UK
Connected to: Apache Hive (version 1.1.0-cdh5.9.3)
Driver: Hive JDBC (version 1.1.0-cdh5.9.3)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://ip-172-31-47-91.eu-west-1.com> show tables;
INFO  : Compiling command(queryId=hive_20171020062525_10d01509-2ac1-4146-90ab-7b7a73fa71f5): show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20171020062525_10d01509-2ac1-4146-90ab-7b7a73fa71f5); Time taken: 0.056 seconds
INFO  : Executing command(queryId=hive_20171020062525_10d01509-2ac1-4146-90ab-7b7a73fa71f5): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171020062525_10d01509-2ac1-4146-90ab-7b7a73fa71f5); Time taken: 0.125 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| sample_07  |
| sample_08  |
+------------+--+

```
