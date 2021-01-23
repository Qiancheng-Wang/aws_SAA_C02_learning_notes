## DynamoDB Authentication

You can authenticate to your DB instance using AWS Identity and Access Management (IAM) database authentication. IAM database authentication works with MySQL and PostgreSQL. With this authentication method, you don't need to use a password when you connect to a DB instance.

An authentication token is a string of characters that you use instead of a password. After you generate an authentication token, it's valid for 15 minutes before it expires. If you try to connect using an expired token, the connection request is denied.

## DynamoDB auto scaling

`DynamoDB auto scaling` uses the AWS Application Auto Scaling service to dynamically adjust provisioned throughput capacity on your behalf, in response to actual traffic patterns.

This enables a table or a global secondary index to increase its provisioned read and write capacity to handle sudden increases in traffic, `without throttling`. When the workload decreases, Application Auto Scaling decreases the throughput so that you don't pay for unused provisioned capacity.

## DynamoDB Trigger and streams.

Amazon DynamoDB is integrated with AWS Lambda so that you can create triggers — pieces of code that automatically respond to events in DynamoDB Streams.

With triggers, you can build applications that react to data modifications in DynamoDB tables.

If you enable `DynamoDB Streams` on a table, you can `associate the stream ARN with a Lambda function that you write`.

Immediately after an item in the table is modified, a new record appears in the table's stream. AWS Lambda polls the stream and invokes your Lambda function synchronously when it detects new stream records.

## DAX

- Fully managed, highly available, in-memory cache.
- 10x performance improvement.
- reduces request time from millisecondes to microseconds - even under load.
- No Need for developers to manage caching logic.
- compatible with DynamoDB API calls.

## On-demand capacity

- diff than provisioned capacity, you `only pay-per-request pricing`. so on-demand capacity is good for balancing your cost and performance.
- no minimum capacity to purchase.
- but on-demand capacity is `pay-more-per-request` than provisioned capacity.

so on-demand capacity is better to use for new product launches where you are not really sure about the traffic or workloads.
Once your application can predict the traffic and consumption, you better use provision capacity rather than on-demand capacity.
