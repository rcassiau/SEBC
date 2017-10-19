* Authenticate your user as a Kerberos principal 
* Use `beeline` to confirm your principal sees no tables
    * `!connect jdbc:hive2://localhost:10000/default;principal=hive/fdqn@REALM.COM`
        * Replace `fqdn` with your host's fully-qualified domain name 
    * Use your Linux account/password to authenticate when prompted
    * Enter `SHOW TABLES;`
    * The statement should return an empty set because no authorizations are in place
* Copy the transcript of this section to `security/labs/sentry-test.md`
```
[root@ip-172-31-39-234 ~]# klist
Ticket cache: FILE:/tmp/krb5cc_0
Default principal: rcassiau@RCASSIAU.IBM

Valid starting       Expires              Service principal
10/19/2017 08:16:31  10/20/2017 08:16:31  krbtgt/RCASSIAU.IBM@RCASSIAU.IBM
	renew until 10/26/2017 08:16:31
[root@ip-172-31-39-234 ~]# beeline
Beeline version 1.1.0-cdh5.9.3 by Apache Hive
beeline> !connect jdbc:hive2://ip-172-31-43-15.eu-west-1.compute.internal:10000/default;principal=hive/ip-172-31-43-15.eu-west-1.compute.internal@RCASSIAU.IBM
scan complete in 2ms
Connecting to jdbc:hive2://ip-172-31-43-15.eu-west-1.compute.internal:10000/default;principal=hive/ip-172-31-43-15.eu-west-1.compute.internal@RCASSIAU.IBM
Connected to: Apache Hive (version 1.1.0-cdh5.9.3)
Driver: Hive JDBC (version 1.1.0-cdh5.9.3)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://ip-172-31-43-15.eu-west-1.com> SHOW TABLES;
INFO  : Compiling command(queryId=hive_20171019082929_b1e728a7-0d32-497d-abc4-3664e6aca419): SHOW TABLES
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20171019082929_b1e728a7-0d32-497d-abc4-3664e6aca419); Time taken: 0.063 seconds
INFO  : Executing command(queryId=hive_20171019082929_b1e728a7-0d32-497d-abc4-3664e6aca419): SHOW TABLES
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171019082929_b1e728a7-0d32-497d-abc4-3664e6aca419); Time taken: 0.137 seconds
INFO  : OK
+-----------+--+
| tab_name  |
+-----------+--+
+-----------+--+
No rows selected (0.287 seconds)
```
* In `beeline`:
    * `CREATE ROLE sentry_admin;`
    * `GRANT ALL ON SERVER server1 TO ROLE sentry_admin;`
    * `GRANT ROLE sentry_admin TO GROUP {your_primary};`
    * `SHOW TABLES;`
* The statement should now return all tables
```
0: jdbc:hive2://ip-172-31-43-15.eu-west-1.com> CREATE ROLE sentry_admin;
INFO  : Compiling command(queryId=hive_20171019083030_58d18ba1-0db5-44a1-a186-3160d7050532): CREATE ROLE sentry_admin
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20171019083030_58d18ba1-0db5-44a1-a186-3160d7050532); Time taken: 0.087 seconds
INFO  : Executing command(queryId=hive_20171019083030_58d18ba1-0db5-44a1-a186-3160d7050532): CREATE ROLE sentry_admin
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171019083030_58d18ba1-0db5-44a1-a186-3160d7050532); Time taken: 0.618 seconds
INFO  : OK
No rows affected (0.72 seconds)
0: jdbc:hive2://ip-172-31-43-15.eu-west-1.com> GRANT ALL ON SERVER server1 TO ROLE sentry_admin;
INFO  : Compiling command(queryId=hive_20171019083131_5dbf72b7-80f3-4b60-b590-bb5783863fb9): GRANT ALL ON SERVER server1 TO ROLE sentry_admin
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20171019083131_5dbf72b7-80f3-4b60-b590-bb5783863fb9); Time taken: 0.076 seconds
INFO  : Executing command(queryId=hive_20171019083131_5dbf72b7-80f3-4b60-b590-bb5783863fb9): GRANT ALL ON SERVER server1 TO ROLE sentry_admin
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171019083131_5dbf72b7-80f3-4b60-b590-bb5783863fb9); Time taken: 0.132 seconds
INFO  : OK
No rows affected (0.222 seconds)
0: jdbc:hive2://ip-172-31-43-15.eu-west-1.com> GRANT ROLE sentry_admin TO GROUP rcassiau;
INFO  : Compiling command(queryId=hive_20171019083131_de86e095-2f4f-4e62-aa1f-154867e9e73e): GRANT ROLE sentry_admin TO GROUP rcassiau
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20171019083131_de86e095-2f4f-4e62-aa1f-154867e9e73e); Time taken: 0.06 seconds
INFO  : Executing command(queryId=hive_20171019083131_de86e095-2f4f-4e62-aa1f-154867e9e73e): GRANT ROLE sentry_admin TO GROUP rcassiau
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171019083131_de86e095-2f4f-4e62-aa1f-154867e9e73e); Time taken: 0.074 seconds
INFO  : OK
No rows affected (0.149 seconds)
0: jdbc:hive2://ip-172-31-43-15.eu-west-1.com> SHOW TABLES;
INFO  : Compiling command(queryId=hive_20171019083131_68d7f635-cad1-4dd2-8ccd-45e84cacfbac): SHOW TABLES
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20171019083131_68d7f635-cad1-4dd2-8ccd-45e84cacfbac); Time taken: 0.059 seconds
INFO  : Executing command(queryId=hive_20171019083131_68d7f635-cad1-4dd2-8ccd-45e84cacfbac): SHOW TABLES
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171019083131_68d7f635-cad1-4dd2-8ccd-45e84cacfbac); Time taken: 0.158 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| customers  |
| sample_07  |
| sample_08  |
| web_logs   |
+------------+--+
4 rows selected (0.299 seconds)
```
* `kinit` as `george`, login to beeline, and use `SHOW TABLES;`
    * `george` should be able to see all tables
```
[root@ip-172-31-39-234 ~]# klist
Ticket cache: FILE:/tmp/krb5cc_0
Default principal: george@RCASSIAU.IBM

Valid starting       Expires              Service principal
10/19/2017 08:35:32  10/20/2017 08:35:32  krbtgt/RCASSIAU.IBM@RCASSIAU.IBM
	renew until 10/26/2017 08:35:32
[root@ip-172-31-39-234 ~]# beeline
Beeline version 1.1.0-cdh5.9.3 by Apache Hive
beeline> !connect jdbc:hive2://ip-172-31-43-15.eu-west-1.compute.internal:10000/default;principal=hive/ip-172-31-43-15.eu-west-1.compute.internal@RCASSIAU.IBM
scan complete in 2ms
Connecting to jdbc:hive2://ip-172-31-43-15.eu-west-1.compute.internal:10000/default;principal=hive/ip-172-31-43-15.eu-west-1.compute.internal@RCASSIAU.IBM
Connected to: Apache Hive (version 1.1.0-cdh5.9.3)
Driver: Hive JDBC (version 1.1.0-cdh5.9.3)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://ip-172-31-43-15.eu-west-1.com> SHOW TABLES;
INFO  : Compiling command(queryId=hive_20171019083636_342cb08b-3dfe-4d30-a309-8c71de59b56c): SHOW TABLES
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20171019083636_342cb08b-3dfe-4d30-a309-8c71de59b56c); Time taken: 0.068 seconds
INFO  : Executing command(queryId=hive_20171019083636_342cb08b-3dfe-4d30-a309-8c71de59b56c): SHOW TABLES
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171019083636_342cb08b-3dfe-4d30-a309-8c71de59b56c); Time taken: 0.135 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| customers  |
| sample_07  |
| sample_08  |
| web_logs   |
+------------+--+
4 rows selected (0.32 seconds)

```
* Repeat the process as `ferdinand`
    * `ferdinand` should see `sample_07` 
```
[root@ip-172-31-39-234 ~]# klist
Ticket cache: FILE:/tmp/krb5cc_0
Default principal: ferdinand@RCASSIAU.IBM

Valid starting       Expires              Service principal
10/19/2017 08:36:42  10/20/2017 08:36:42  krbtgt/RCASSIAU.IBM@RCASSIAU.IBM
	renew until 10/26/2017 08:36:42
[root@ip-172-31-39-234 ~]# beeline
Beeline version 1.1.0-cdh5.9.3 by Apache Hive
beeline> !connect jdbc:hive2://ip-172-31-43-15.eu-west-1.compute.internal:10000/default;principal=hive/ip-172-31-43-15.eu-west-1.compute.internal@RCASSIAU.IBM
scan complete in 1ms
Connecting to jdbc:hive2://ip-172-31-43-15.eu-west-1.compute.internal:10000/default;principal=hive/ip-172-31-43-15.eu-west-1.compute.internal@RCASSIAU.IBM
Connected to: Apache Hive (version 1.1.0-cdh5.9.3)
Driver: Hive JDBC (version 1.1.0-cdh5.9.3)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://ip-172-31-43-15.eu-west-1.com> SHOW TABLES;
INFO  : Compiling command(queryId=hive_20171019083636_3800ca8e-8792-460e-ab01-a988decca312): SHOW TABLES
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20171019083636_3800ca8e-8792-460e-ab01-a988decca312); Time taken: 0.082 seconds
INFO  : Executing command(queryId=hive_20171019083636_3800ca8e-8792-460e-ab01-a988decca312): SHOW TABLES
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171019083636_3800ca8e-8792-460e-ab01-a988decca312); Time taken: 0.245 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| sample_07  |
+------------+--+
1 row selected (0.481 seconds)
```
