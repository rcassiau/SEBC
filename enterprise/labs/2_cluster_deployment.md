```
[root@ip-172-31-43-15 ~]# curl -u rcassiau:cloudera http://ec2-34-253-82-44.eu-west-1.compute.amazonaws.com:7180/api/v2/cm/deployment
{
  "timestamp" : "2017-10-18T09:34:31.748Z",
  "clusters" : [ {
    "name" : "rcassiau",
    "version" : "CDH5",
    "services" : [ {
      "name" : "hive",
      "type" : "HIVE",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "HIVEMETASTORE",
          "items" : [ {
            "name" : "hive_metastore_java_heapsize",
            "value" : "723517440"
          } ]
        }, {
          "roleType" : "HIVESERVER2",
          "items" : [ {
            "name" : "hiveserver2_java_heapsize",
            "value" : "723517440"
          }, {
            "name" : "hiveserver2_spark_driver_memory",
            "value" : "966367641"
          }, {
            "name" : "hiveserver2_spark_executor_cores",
            "value" : "4"
          }, {
            "name" : "hiveserver2_spark_executor_memory",
            "value" : "4402079334"
          }, {
            "name" : "hiveserver2_spark_yarn_driver_memory_overhead",
            "value" : "102"
          }, {
            "name" : "hiveserver2_spark_yarn_executor_memory_overhead",
            "value" : "740"
          } ]
        } ],
        "items" : [ {
          "name" : "hive_metastore_database_host",
          "value" : "ip-172-31-43-15.eu-west-1.compute.internal"
        }, {
          "name" : "hive_metastore_database_name",
          "value" : "hive"
        }, {
          "name" : "hive_metastore_database_password",
          "value" : "hive"
        }, {
          "name" : "mapreduce_yarn_service",
          "value" : "yarn"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hive-GATEWAY-22125033ddf00762cd84890c0c828847",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "b8284280-cba6-4268-9a9f-e44720200db1"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-HIVEMETASTORE-4879d29208cc20f75ebd79830f6ae725",
        "type" : "HIVEMETASTORE",
        "hostRef" : {
          "hostId" : "i-0042ecef15273781a"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "dch1yyqw2f2c7fbfsetwsg0pm"
          } ]
        }
      }, {
        "name" : "hive-HIVESERVER2-4879d29208cc20f75ebd79830f6ae725",
        "type" : "HIVESERVER2",
        "hostRef" : {
          "hostId" : "i-0042ecef15273781a"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "365ygabcza0tddb1nkg0gjaru"
          } ]
        }
      } ],
      "displayName" : "Hive"
    }, {
      "name" : "zookeeper",
      "type" : "ZOOKEEPER",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "SERVER",
          "items" : [ {
            "name" : "dataDir",
            "value" : "/data/zookeeper"
          }, {
            "name" : "dataLogDir",
            "value" : "/data/zookeeper"
          }, {
            "name" : "zookeeper_server_java_heapsize",
            "value" : "723517440"
          } ]
        } ],
        "items" : [ {
          "name" : "zookeeper_datadir_autocreate",
          "value" : "true"
        } ]
      },
      "roles" : [ {
        "name" : "zookeeper-SERVER-22125033ddf00762cd84890c0c828847",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "b8284280-cba6-4268-9a9f-e44720200db1"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "7k97hcjs29vrliu2seavln1hc"
          }, {
            "name" : "serverId",
            "value" : "1"
          } ]
        }
      }, {
        "name" : "zookeeper-SERVER-4879d29208cc20f75ebd79830f6ae725",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "i-0042ecef15273781a"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "46l4y7f7hzchu12mdovuhcqm2"
          }, {
            "name" : "serverId",
            "value" : "2"
          } ]
        }
      }, {
        "name" : "zookeeper-SERVER-8d8c55f8cd0f15d7607a396e6edcf95f",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "990ea740-317e-478d-abb1-6f7f301dfc85"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "5w5b602mofeijd8rvc99t9ys1"
          }, {
            "name" : "serverId",
            "value" : "3"
          } ]
        }
      } ],
      "displayName" : "ZooKeeper"
    }, {
      "name" : "hue",
      "type" : "HUE",
      "config" : {
        "roleTypeConfigs" : [ ],
        "items" : [ {
          "name" : "database_host",
          "value" : "ip-172-31-43-15.eu-west-1.compute.internal"
        }, {
          "name" : "database_password",
          "value" : "hue"
        }, {
          "name" : "database_type",
          "value" : "mysql"
        }, {
          "name" : "hive_service",
          "value" : "hive"
        }, {
          "name" : "hue_webhdfs",
          "value" : "hdfs-HTTPFS-4879d29208cc20f75ebd79830f6ae725"
        }, {
          "name" : "oozie_service",
          "value" : "oozie"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hue-HUE_SERVER-4879d29208cc20f75ebd79830f6ae725",
        "type" : "HUE_SERVER",
        "hostRef" : {
          "hostId" : "i-0042ecef15273781a"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "k3jc14u2ji30fc6mgy5tmzxk"
          }, {
            "name" : "secret_key",
            "value" : "LxGc6e8Q3hOR8oHA62PuT8HncTH4oC"
          } ]
        }
      } ],
      "displayName" : "Hue"
    }, {
      "name" : "oozie",
      "type" : "OOZIE",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "OOZIE_SERVER",
          "items" : [ {
            "name" : "oozie_database_host",
            "value" : "ip-172-31-43-15.eu-west-1.compute.internal"
          }, {
            "name" : "oozie_database_password",
            "value" : "oozie"
          }, {
            "name" : "oozie_database_type",
            "value" : "mysql"
          }, {
            "name" : "oozie_database_user",
            "value" : "oozie"
          }, {
            "name" : "oozie_java_heapsize",
            "value" : "723517440"
          } ]
        } ],
        "items" : [ {
          "name" : "hive_service",
          "value" : "hive"
        }, {
          "name" : "mapreduce_yarn_service",
          "value" : "yarn"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "oozie-OOZIE_SERVER-4879d29208cc20f75ebd79830f6ae725",
        "type" : "OOZIE_SERVER",
        "hostRef" : {
          "hostId" : "i-0042ecef15273781a"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "3ntods03m3l657gtp24dxnjdx"
          } ]
        }
      } ],
      "displayName" : "Oozie"
    }, {
      "name" : "yarn",
      "type" : "YARN",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "GATEWAY",
          "items" : [ {
            "name" : "mapred_reduce_tasks",
            "value" : "6"
          }, {
            "name" : "mapred_submit_replication",
            "value" : "1"
          } ]
        }, {
          "roleType" : "NODEMANAGER",
          "items" : [ {
            "name" : "rm_cpu_shares",
            "value" : "1800"
          }, {
            "name" : "rm_io_weight",
            "value" : "900"
          }, {
            "name" : "yarn_nodemanager_heartbeat_interval_ms",
            "value" : "100"
          }, {
            "name" : "yarn_nodemanager_local_dirs",
            "value" : "/data/yarn/nm"
          }, {
            "name" : "yarn_nodemanager_log_dirs",
            "value" : "/data/yarn/container-logs"
          }, {
            "name" : "yarn_nodemanager_resource_cpu_vcores",
            "value" : "3"
          }, {
            "name" : "yarn_nodemanager_resource_memory_mb",
            "value" : "3376"
          } ]
        }, {
          "roleType" : "RESOURCEMANAGER",
          "items" : [ {
            "name" : "resource_manager_java_heapsize",
            "value" : "723517440"
          }, {
            "name" : "yarn_scheduler_maximum_allocation_mb",
            "value" : "4939"
          }, {
            "name" : "yarn_scheduler_maximum_allocation_vcores",
            "value" : "3"
          } ]
        } ],
        "items" : [ {
          "name" : "hdfs_service",
          "value" : "hdfs"
        }, {
          "name" : "rm_dirty",
          "value" : "false"
        }, {
          "name" : "rm_last_allocation_percentage",
          "value" : "90"
        }, {
          "name" : "yarn_service_cgroups",
          "value" : "false"
        }, {
          "name" : "yarn_service_lce_always",
          "value" : "false"
        }, {
          "name" : "zk_authorization_secret_key",
          "value" : "KKtThKBp7k7g5LkUGgPMwqQrN7IX2z"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "yarn-JOBHISTORY-22125033ddf00762cd84890c0c828847",
        "type" : "JOBHISTORY",
        "hostRef" : {
          "hostId" : "b8284280-cba6-4268-9a9f-e44720200db1"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "3g9d3puedd76z5t58epavup5h"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-5b849b3acbb06d53dd7c975a3501be47",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "fd48f985-76ed-4530-8b55-922fae47475b"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "jcvvlhvhkwxgqpixuxwn1x5f"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-8d8c55f8cd0f15d7607a396e6edcf95f",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "990ea740-317e-478d-abb1-6f7f301dfc85"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "am30szpra03qx0kpbw2wspada"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-fe2a3822082003f65b7840ef07ebb6bd",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "b9537021-08a4-4463-af9c-00025f73052d"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "jxl805rob3ce0a0v5bcsvjv3"
          } ]
        }
      }, {
        "name" : "yarn-RESOURCEMANAGER-22125033ddf00762cd84890c0c828847",
        "type" : "RESOURCEMANAGER",
        "hostRef" : {
          "hostId" : "b8284280-cba6-4268-9a9f-e44720200db1"
        },
        "config" : {
          "items" : [ {
            "name" : "rm_id",
            "value" : "50"
          }, {
            "name" : "role_jceks_password",
            "value" : "6xynmmc57rscpv7evc4e86gil"
          } ]
        }
      }, {
        "name" : "yarn-RESOURCEMANAGER-4879d29208cc20f75ebd79830f6ae725",
        "type" : "RESOURCEMANAGER",
        "hostRef" : {
          "hostId" : "i-0042ecef15273781a"
        },
        "config" : {
          "items" : [ {
            "name" : "rm_id",
            "value" : "41"
          }, {
            "name" : "role_jceks_password",
            "value" : "3hugr7hykcgzn9740mr8s6qt6"
          } ]
        }
      } ],
      "displayName" : "YARN (MR2 Included)"
    }, {
      "name" : "hdfs",
      "type" : "HDFS",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "DATANODE",
          "items" : [ {
            "name" : "datanode_java_heapsize",
            "value" : "1073741824"
          }, {
            "name" : "dfs_data_dir_list",
            "value" : "/data/dfs/dn"
          }, {
            "name" : "dfs_datanode_du_reserved",
            "value" : "4292765696"
          }, {
            "name" : "dfs_datanode_max_locked_memory",
            "value" : "4294967296"
          }, {
            "name" : "rm_cpu_shares",
            "value" : "200"
          }, {
            "name" : "rm_io_weight",
            "value" : "100"
          } ]
        }, {
          "roleType" : "GATEWAY",
          "items" : [ {
            "name" : "dfs_client_use_trash",
            "value" : "true"
          } ]
        }, {
          "roleType" : "JOURNALNODE",
          "items" : [ {
            "name" : "dfs_journalnode_edits_dir",
            "value" : "/data/dfs/jn"
          } ]
        }, {
          "roleType" : "NAMENODE",
          "items" : [ {
            "name" : "dfs_name_dir_list",
            "value" : "/data/dfs/nn"
          }, {
            "name" : "dfs_namenode_servicerpc_address",
            "value" : "8022"
          } ]
        }, {
          "roleType" : "SECONDARYNAMENODE",
          "items" : [ {
            "name" : "fs_checkpoint_dir_list",
            "value" : "/data/dfs/snn"
          } ]
        } ],
        "items" : [ {
          "name" : "dfs_ha_fencing_cloudera_manager_secret_key",
          "value" : "Q0JmbDXmbz2Mf2ZHaO0nIh3Vby4DLx"
        }, {
          "name" : "dfs_ha_fencing_methods",
          "value" : "shell(true)"
        }, {
          "name" : "fc_authorization_secret_key",
          "value" : "3bN4cy37BNnHyu1RHArkH12sxdDG0U"
        }, {
          "name" : "http_auth_signature_secret",
          "value" : "zepC9PakR5BuofIWtmnPgJ8g99S32t"
        }, {
          "name" : "rm_dirty",
          "value" : "false"
        }, {
          "name" : "rm_last_allocation_percentage",
          "value" : "10"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hdfs-BALANCER-22125033ddf00762cd84890c0c828847",
        "type" : "BALANCER",
        "hostRef" : {
          "hostId" : "b8284280-cba6-4268-9a9f-e44720200db1"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hdfs-DATANODE-5b849b3acbb06d53dd7c975a3501be47",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "fd48f985-76ed-4530-8b55-922fae47475b"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "75sbdootffy0c17bvv0bzglar"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-8d8c55f8cd0f15d7607a396e6edcf95f",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "990ea740-317e-478d-abb1-6f7f301dfc85"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "92vu3lzn0rf8x49umn7rhi827"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-fe2a3822082003f65b7840ef07ebb6bd",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "b9537021-08a4-4463-af9c-00025f73052d"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "c2g6ih51se5402hq2j1oiuraw"
          } ]
        }
      }, {
        "name" : "hdfs-FAILOVERCONTROLLER-22125033ddf00762cd84890c0c828847",
        "type" : "FAILOVERCONTROLLER",
        "hostRef" : {
          "hostId" : "b8284280-cba6-4268-9a9f-e44720200db1"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "d3r4hi20ypk5jpnt0owjg2atp"
          } ]
        }
      }, {
        "name" : "hdfs-FAILOVERCONTROLLER-4879d29208cc20f75ebd79830f6ae725",
        "type" : "FAILOVERCONTROLLER",
        "hostRef" : {
          "hostId" : "i-0042ecef15273781a"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "c78gjz8eydr3wngwo012670gx"
          } ]
        }
      }, {
        "name" : "hdfs-GATEWAY-22125033ddf00762cd84890c0c828847",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "b8284280-cba6-4268-9a9f-e44720200db1"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hdfs-HTTPFS-4879d29208cc20f75ebd79830f6ae725",
        "type" : "HTTPFS",
        "hostRef" : {
          "hostId" : "i-0042ecef15273781a"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "dwavv4vcgizri4to4xzd1hhad"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-22125033ddf00762cd84890c0c828847",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "b8284280-cba6-4268-9a9f-e44720200db1"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "3gj4darwsrqmll0o8v8stmgj7"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-4879d29208cc20f75ebd79830f6ae725",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "i-0042ecef15273781a"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "6kqqgpebpzynnue8t9gxiecrn"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-8d8c55f8cd0f15d7607a396e6edcf95f",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "990ea740-317e-478d-abb1-6f7f301dfc85"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "6pj93r5dojhtehxc9m9cuqga8"
          } ]
        }
      }, {
        "name" : "hdfs-NAMENODE-22125033ddf00762cd84890c0c828847",
        "type" : "NAMENODE",
        "hostRef" : {
          "hostId" : "b8284280-cba6-4268-9a9f-e44720200db1"
        },
        "config" : {
          "items" : [ {
            "name" : "autofailover_enabled",
            "value" : "true"
          }, {
            "name" : "dfs_federation_namenode_nameservice",
            "value" : "nameservice1"
          }, {
            "name" : "dfs_namenode_quorum_journal_name",
            "value" : "nameservice1"
          }, {
            "name" : "namenode_id",
            "value" : "56"
          }, {
            "name" : "role_jceks_password",
            "value" : "7n3jd8xj9fzb3vzfid0kc7xo6"
          } ]
        }
      }, {
        "name" : "hdfs-NAMENODE-4879d29208cc20f75ebd79830f6ae725",
        "type" : "NAMENODE",
        "hostRef" : {
          "hostId" : "i-0042ecef15273781a"
        },
        "config" : {
          "items" : [ {
            "name" : "autofailover_enabled",
            "value" : "true"
          }, {
            "name" : "dfs_federation_namenode_nameservice",
            "value" : "nameservice1"
          }, {
            "name" : "dfs_namenode_quorum_journal_name",
            "value" : "nameservice1"
          }, {
            "name" : "namenode_id",
            "value" : "44"
          }, {
            "name" : "role_jceks_password",
            "value" : "9jiq0glitnz66erquxsaz5pml"
          } ]
        }
      } ],
      "displayName" : "HDFS"
    } ]
  } ],
  "hosts" : [ {
    "hostId" : "990ea740-317e-478d-abb1-6f7f301dfc85",
    "ipAddress" : "172.31.38.222",
    "hostname" : "ip-172-31-38-222.eu-west-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ {
        "name" : "memory_overcommit_threshold",
        "value" : "0.9"
      } ]
    }
  }, {
    "hostId" : "b8284280-cba6-4268-9a9f-e44720200db1",
    "ipAddress" : "172.31.39.234",
    "hostname" : "ip-172-31-39-234.eu-west-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "b9537021-08a4-4463-af9c-00025f73052d",
    "ipAddress" : "172.31.41.242",
    "hostname" : "ip-172-31-41-242.eu-west-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "i-0042ecef15273781a",
    "ipAddress" : "172.31.43.15",
    "hostname" : "ip-172-31-43-15.eu-west-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ {
        "name" : "memory_overcommit_threshold",
        "value" : "0.9"
      } ]
    }
  }, {
    "hostId" : "fd48f985-76ed-4530-8b55-922fae47475b",
    "ipAddress" : "172.31.46.129",
    "hostname" : "ip-172-31-46-129.eu-west-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  } ],
  "users" : [ {
    "name" : "__cloudera_internal_user__mgmt-EVENTSERVER-4879d29208cc20f75ebd79830f6ae725",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "4eaecafc4034785130784c322fc67e89abfb702db168becf3654a3c510619633",
    "pwSalt" : 4946163707965512253,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-HOSTMONITOR-4879d29208cc20f75ebd79830f6ae725",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "16b5a3f52fa6df91bd33c7b5c1b018d94fe082bb7860ec7ad57729abc2bc10e9",
    "pwSalt" : 5125902039811593094,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-REPORTSMANAGER-4879d29208cc20f75ebd79830f6ae725",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "d99268d1f5d6142c49130d2a7a3f6304dfaa27e51e0c50c3b394894e05c55cbf",
    "pwSalt" : -4933792715705705175,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-SERVICEMONITOR-4879d29208cc20f75ebd79830f6ae725",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "a2509c09f3eb3b4b7fdb17e9427665b623fc2d1fcfdd2ff6a78e51aa310f0380",
    "pwSalt" : 6786911589088749462,
    "pwLogin" : true
  }, {
    "name" : "admin",
    "roles" : [ "ROLE_LIMITED" ],
    "pwHash" : "4cd1412f1b1cfcd6b16e88d74443c1a31e69470cf719a026fcf954f799c7973c",
    "pwSalt" : -6962175268528291002,
    "pwLogin" : true
  }, {
    "name" : "minotaur",
    "roles" : [ "ROLE_CONFIGURATOR" ],
    "pwHash" : "1be298dcbacd04cd7697c7908f287180636d1f1f4e58910dd4a32d1edce9735d",
    "pwSalt" : -2819442198147496855,
    "pwLogin" : true
  }, {
    "name" : "rcassiau",
    "roles" : [ "ROLE_ADMIN" ],
    "pwHash" : "212c297d40d4d20c6efaba74516ad7c65c02d3208c4e262088e7c8cd7f5ca5b9",
    "pwSalt" : 2042151025485035818,
    "pwLogin" : true
  } ],
  "versionInfo" : {
    "version" : "5.8.3",
    "buildUser" : "jenkins",
    "buildTimestamp" : "20161019-1013",
    "gitHash" : "518f0d6d44abc87bc392646e4369a20c8192b7cf",
    "snapshot" : false
  },
  "managementService" : {
    "name" : "mgmt",
    "type" : "MGMT",
    "config" : {
      "roleTypeConfigs" : [ {
        "roleType" : "EVENTSERVER",
        "items" : [ {
          "name" : "event_server_heapsize",
          "value" : "723517440"
        } ]
      }, {
        "roleType" : "HOSTMONITOR",
        "items" : [ {
          "name" : "firehose_non_java_memory_bytes",
          "value" : "1610612736"
        } ]
      }, {
        "roleType" : "REPORTSMANAGER",
        "items" : [ {
          "name" : "headlamp_database_host",
          "value" : "ip-172-31-43-15.eu-west-1.compute.internal"
        }, {
          "name" : "headlamp_database_name",
          "value" : "rman"
        }, {
          "name" : "headlamp_database_password",
          "value" : "rman"
        }, {
          "name" : "headlamp_database_user",
          "value" : "rman"
        }, {
          "name" : "headlamp_heapsize",
          "value" : "723517440"
        } ]
      }, {
        "roleType" : "SERVICEMONITOR",
        "items" : [ {
          "name" : "firehose_non_java_memory_bytes",
          "value" : "1610612736"
        } ]
      } ],
      "items" : [ ]
    },
    "roles" : [ {
      "name" : "mgmt-ALERTPUBLISHER-4879d29208cc20f75ebd79830f6ae725",
      "type" : "ALERTPUBLISHER",
      "hostRef" : {
        "hostId" : "i-0042ecef15273781a"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "1qol0ze8ipxmg10p32ors10iq"
        } ]
      }
    }, {
      "name" : "mgmt-EVENTSERVER-4879d29208cc20f75ebd79830f6ae725",
      "type" : "EVENTSERVER",
      "hostRef" : {
        "hostId" : "i-0042ecef15273781a"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "9mm8de6ett95lir1v1ft01qkf"
        } ]
      }
    }, {
      "name" : "mgmt-HOSTMONITOR-4879d29208cc20f75ebd79830f6ae725",
      "type" : "HOSTMONITOR",
      "hostRef" : {
        "hostId" : "i-0042ecef15273781a"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "bkuoyzeycwf8h9hzw1tbpjcq8"
        } ]
      }
    }, {
      "name" : "mgmt-REPORTSMANAGER-4879d29208cc20f75ebd79830f6ae725",
      "type" : "REPORTSMANAGER",
      "hostRef" : {
        "hostId" : "i-0042ecef15273781a"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "cflwxb8wulbf0snz7zukb2nvz"
        } ]
      }
    }, {
      "name" : "mgmt-SERVICEMONITOR-4879d29208cc20f75ebd79830f6ae725",
      "type" : "SERVICEMONITOR",
      "hostRef" : {
        "hostId" : "i-0042ecef15273781a"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "25qvnr8oumz1wdv4cupxm2dg8"
        } ]
      }
    } ],
    "displayName" : "Cloudera Management Service"
  },
  "managerSettings" : {
    "items" : [ {
      "name" : "CLUSTER_STATS_START",
      "value" : "10/23/2012 2:10"
    }, {
      "name" : "PUBLIC_CLOUD_STATUS",
      "value" : "ON_PUBLIC_CLOUD"
    }, {
      "name" : "REMOTE_PARCEL_REPO_URLS",
      "value" : "https://archive.cloudera.com/cdh5/parcels/{latest_supported}/,http://ec2-34-253-82-44.eu-west-1.compute.amazonaws.com/cdh5/parcels/{latest_supported}/,https://archive.cloudera.com/cdh5/parcels/5.8.3/,https://archive.cloudera.com/cdh4/parcels/latest/,https://archive.cloudera.com/impala/parcels/latest/,https://archive.cloudera.com/search/parcels/latest/,https://archive.cloudera.com/accumulo/parcels/1.4/,https://archive.cloudera.com/accumulo-c5/parcels/latest/,https://archive.cloudera.com/kafka/parcels/latest/,https://archive.cloudera.com/navigator-keytrustee5/parcels/latest/,https://archive.cloudera.com/spark/parcels/latest/,https://archive.cloudera.com/sqoop-connectors/parcels/latest/"
    }, {
      "name" : "SESSION_TIMEOUT",
      "value" : "28800"
    } ]
  }
```
