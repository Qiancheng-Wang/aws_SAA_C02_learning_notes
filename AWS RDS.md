Amazon RDS automatically performs a failover in the event of any of the following:

1. Loss of availability in primary Availability Zone

2. Loss of network connectivity to primary

3. Compute unit failure on primary

4. Storage failure on primary

The following options are incorrect because all these scenarios do not affect the primary database. Automatic failover only occurs if the primary database is the one that is affected.

- Storage failure on secondary DB instance

- In the event of Read Replica failure

- Compute unit failure on secondary DB instance

## RDS Enhanced Monitoring Metrics

In RDS, the Enhanced Monitoring metrics shown in the Process List view are organized as follows:

`RDS child processes` – Shows a summary of the RDS processes that support the DB instance, for example aurora for Amazon Aurora DB clusters and mysqld for MySQL DB instances. Process threads appear nested beneath the parent process. Process threads show CPU utilization only as other metrics are the same for all threads for the process. The console displays a maximum of 100 processes and threads. The results are a combination of the top CPU consuming and memory consuming processes and threads. If there are more than 50 processes and more than 50 threads, the console displays the top 50 consumers in each category. This display helps you identify which processes are having the greatest impact on performance.

`RDS processes` – Shows a summary of the resources used by the RDS management agent, diagnostics monitoring processes, and other AWS processes that are required to support RDS DB instances.

`OS processes` – Shows a summary of the kernel and system processes, which generally have minimal impact on performance.

## There are 2 ways to use SSL to connect to your SQL Server DB instance:

- Force SSL for all connections — this happens transparently to the client, and the client doesn't have to do any work to use SSL.

- Encrypt specific connections — this sets up an SSL connection from a specific client computer, and you must do work on the client to encrypt connections. Download the Amazon RDS Root CA certificate. Import the certificate to your servers and configure your application to use SSL to encrypt the connection to RDS.

## RDS Metrics Monitoring

Amazon RDS provides metrics in real time for the operating system (OS) that your DB instance runs on.

You can view the metrics for your DB instance using the console, or consume the `Enhanced Monitoring` JSON output from CloudWatch Logs in a monitoring system of your choice.

By default, Enhanced Monitoring metrics are `stored in the CloudWatch Logs for 30 days`. To modify the amount of time the metrics are stored in the CloudWatch Logs, change the `retention` for the RDSOSMetrics log group in the CloudWatch console.

## differences between CloudWatch and Enhanced Monitoring Metrics:

CloudWatch gathers metrics about `CPU utilization` from the `hypervisor for a DB instance.`

Enhanced Monitoring gathers its `metrics` from `an agent on the instance`.

As a result, you might find differences between the measurements, because the hypervisor layer performs a small amount of work.

The differences can be greater if your DB instances use smaller instance classes, because then there are likely more virtual machines (VMs) that are managed by the hypervisor layer on a single physical instance.

Enhanced Monitoring metrics are useful when you want to see how different processes or threads on a DB instance use the CPU.

## RDS Failover Pattern

In Amazon RDS, failover is automatically handled so that you can resume database operations as quickly as possible without administrative intervention in the event that your primary database instance went down.

When failing over, Amazon RDS simply flips the `canonical name record (CNAME)` for your DB instance to point at the standby, which is in turn promoted to become the new primary.

![RDS Failover Pattern](assets/rds_ha_5.png)
