### Redis-as-a-Service in SAP Multi-Cloud PLatform
SAP Cloud Platform is an open platform-as-a-service (PaaS) product that provides core platform and backing services, for building and extending cloud applications on multiple cloud infrastructure providers. 

   ```sh
SCP's fully managed Redis-as-a-service consists of 3 VMs - 1 Master and 2-Slaves. Data replication is done asynchronously between master and slaves with minimum one slave in sync with master thorughout instance lifecycle.
   ``` 
### Major Features

### End-user configurable policies like Eviction and save 
Redis applications users can provide the values of policies favoring their use-case during instance-creation.
### Bi-weekly-Rolling-Updates-with-Near-Zero-Downtime:
Redis sentinels backed by various custom scripts enables service to be available even during updates. 
### Persistence enabled cluster 
RDB based persistence allows application to use as data store and not just cache.

### Multiple-Plans-to-support-different-use-cases

### Disaster-Recovery-using-Backup-and-Restore: 
Redis-as-a-Service instance provides snapshot based backup and restore mechanism. Snapshots are stored on cloud storage in AWS/Azure/GCP. Backups are scheduled and service remains available during backup. Recovery process involves creation of volume from snapshot and attaching that volume to the master node.
### Centralized-Monitoring-System/Metrics-Collector
A monitoring agent runs as job in every Redis VM to report its service health metrics like service-availability|CPU|memory|disk-usage, and database information like stored keys, maxmemory utilization. The monitoring agent collects this information and reports it to centralized monitoring server, which stores in a time-series-database. A monitoring-web-application shows metrics via various charts so that devops can identify the instance health at any given time-date range
![N|Solid](https://github.com/ankita0811/RedisConf/blob/master/redis-dashboard.png?raw=true)

### Centralized-Troubleshooting-System-for-all-Redis-as-a-Service-instance
All important system-logs and custom logs generated from a service-instance is pushed to a central system so that Ops can access them to trace any condition/debug any problems.
Troubleshooter lets users debug any issue irrespective of service-instance availability.

![N|Solid](https://github.com/ankita0811/RedisConf/blob/master/redis-logging.png?raw=true)




### Multi-channel-Alerting-System
Alerting-module raise alerts when some undesired state is reported, like "redis-server-not-available, maxmemory-size-threshold-crossed, backup-failed" among others.
![N|Solid](https://github.com/ankita0811/RedisConf/blob/master/alert-redis.png?raw=true)

