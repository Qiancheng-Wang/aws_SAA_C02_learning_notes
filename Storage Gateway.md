## Different types of Storage Gateway

1. `Tape Gateway`: this is just a cost-effective, durable, long-term offsite alternative for data archiving, which is not needed in this scenario.

2. `File Gateway`: File Gateway is used to store and retrieve Amazon S3 objects through NFS and SMB protocols.

## Cached Mode vs Stored Mode in Volume Gateway

By using cached volumes, you can use Amazon `S3 as your primary data storage`, while `retaining frequently accessed data locally in your storage gateway`.

Cached volumes minimize the need to scale your on-premises storage infrastructure, while still providing your applications with low-latency access to frequently accessed data.

You can create storage volumes up to 32 TiB in size and afterward, attach these volumes as iSCSI devices to your on-premises application servers. When you write to these volumes, your gateway stores the data in Amazon S3. It retains the recently read data in your on-premises storage gateway's cache and uploads buffer storage.

In the cached volumes solution, AWS Storage Gateway stores all your on-premises application data in a storage volume in Amazon S3. Hence, the correct answer is: Volume Gateway in cached mode.

**While `Stored Volumes` are used if you need low-latency access to your entire dataset.Stored Volumes are used if you need `low-latency access to your entire dataset`.**
