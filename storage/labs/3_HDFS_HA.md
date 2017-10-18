* Use the Cloudera Manager wizard to enable HA
    * Once configured, get a screenshot of the HDFS Instances tab
        * Hint: Follow closely the [Enabling HDFS HA Using Cloudera Manager](https://www.cloudera.com/documentation/enterprise/latest/topics/cdh_hag_hdfs_ha_enabling.html) instructions. There's more work that needs to be done besides running the wizard.
		- HA for HDFS have been activated. and Hive Metastore namenode has been updated 
* Add a CM user and name it with your GitHub handle
    * Assign the `Full Administrator` role to this user
    * Assign the password `cloudera` to this user
    * Re-assign the `admin` user to the `Limited Operator` role
    * Take a screenshot of your users page; save it to `storage/labs/4_CM_users.png`
* In an Issue comment, post the URL to your Cloudera Manager instance
