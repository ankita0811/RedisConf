### Redis-as-a-Service in SAP Multi-Cloud PLatform

SAP Cloud Platform is an open platform-as-a-service (PaaS) product that provides core platform and backing services, for building and extending cloud applications on multiple cloud infrastructure providers.

    One of the core services provided by SCP is Redis-as-a-service.Each Redis-as-a-Service instance consists of 3 VMs- Master and 2-Slaves. 

SCP manages 1000+ Redis-as-a-Service instances across multiple IAASs. 


### Setup-And-Configuration


### End-user configurable parameters
eviction , save
Persistence enabled
### Bi-weekly-Rolling-Updates-with-Near-Zero-Downtime

Data consistency always with min_slave_to_write always 1


### Disaster-Recovery/Data-Protection-using-Backup-and-Restore



### Centralized-Monitoring-System/Metrics-Collector

MT-PostgreSQL-as-a-Service supports tenant level health monitoring. Monitoring agent running on instance reports health of every tenant. It reports metrics like bulk reads, bulk writes, connections used etc. It also reports various system specific metrics like CPU, Memory, Disk usage etc.

The monitoring agent collects this information and reports it to centralized monitoring server, which stores in a time-series-database. A monitoring-web-application shows metrics via various charts so that devops can identify the tenant health at any given time-date range.

### Centralized-Troubleshooting-System-for-all-Redis-as-a-Service-instance


MT-PostgreSQL-as-a-Service supports tenant based logging for audit and troubleshooting purposes. Tenant database logs are pushed to a centralized system, enabling dev ops to debug any issue irrespective of instance availability.

![N|Solid](https://github.com/ankita0811/PostgresqlConf/blob/master/elk.png?raw=true)

### Multi-channel-Alerting-System
Alerting-module raise alerts when some undesired state is reported, like primary-server-not-available, replication-down, disk-size-threshold-crossed, backup-failed etc.

![N|Solid](https://github.com/ankita0811/PostgresqlConf/blob/master/avs.png?raw=true)
![N|Solid](https://github.com/ankita0811/PostgresqlConf/blob/master/alert.png?raw=true) 

