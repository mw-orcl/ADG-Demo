# Active Data Guard to OCI Demo #

## Demo Overview ##

Oracle’s Maximum Availability Architecture (Oracle MAA) is the best practices blueprint for data protection and availability for Oracle databases deployed on private, public or hybrid clouds. Data Guard and Active Data Guard provide disaster recovery (DR) for databases with recovery time objectives (RTO) that cannot be met by restoring from backup. Customers use these solutions to deploy one or more synchronized replicas (standby databases) of a production database (the primary database) in physically separate locations to provide high availability, comprehensive data protection, and disaster recovery for mission-critical data. 

An effective disaster recovery plan can be costly due to the need to establish, equip and manage a remote data center. The Oracle Cloud offers a great alternative for hosting standby databases for customers who do not have a DR site or who prefer not to deal with the cost or complexity of managing a remote data center. Existing production databases remain on-premises and standby databases used for DR are deployed on the Oracle Cloud. This mode of deployment is commonly referred to as a hybrid cloud implementation. 

## Demo

In this Active Data Guard demo the primary is a compute instance on the Oracle CIoud. It's used to simulate the on-premise database, which is deployed in one region (For example: Toronto). The standby is the Oracle Database Cloud service and is deployed in another region (For example: Montreal). The primary and the standby database communicate through the public internet and is configured to communicate bi-directionally.  We will demonstrate the following:

1. **Transaction Replication from Primary to Standby**

From on-premise side, insert and commit some data.  The standby side will have the transaction replicated in seconds.

​	2. **DML Redirect**

Starting  with Oracle DB 19c, we can run DML operations on Active Data Guard standby databases. This enables you to occasionally execute DMLs on read-mostly applications on the standby database.  DML operations are automatically redirected to the primary database.

​	3. **Switchover to the Cloud** 

At any time, you can manually execute a Data Guard switchover (planned event) or failover (unplanned event).  Switchover and failover reverse the roles of the databases in a Data Guard configuration – the standby in the cloud becomes the primary and the original on-premise primary becomes a standby database.  

​	4. **Failover and Reinstate** 

This section describes the content of the lab. You can explain a bit what it will do and what to end-goal is.

## Access the Demo ##

The demo is on the oraclepartnersas tenancy.

In the compartment MWAN in region Toronto is a compute which is acting as the on-premise 19c database.

- ​	On prem IP address: 140.238.148.203

In the compartment MWAN in region Montreal is the DBCS cloud database.

- ​	Cloud database IP address is: 168.138.67.93
- ​	DB unique name is: ORCL_yul1qq

