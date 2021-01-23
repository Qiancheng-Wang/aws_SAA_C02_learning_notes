Amazon Kinesis Data Firehose is a fully managed service for delivering real-time streaming data.

Firehose is fully managed (i.e. scales automatically) whereas Streams is manually managed.

Second, Firehose only goes to S3 or RedShift, whereas Streams can go to other services.

With Kinesis Streams, you build applications using the Kinesis Producer Library put the data into a stream and then process it with an application that uses the Kinesis Client Library and with Kinesis Connector Library send the processed data to S3, Redshift, DynamoDB etc.

With Kinesis Firehose it’s a bit simpler where you create the delivery stream and send the data to S3, Redshift or ElasticSearch (using the Kinesis Agent or API) directly and storing it in those services.

Kinesis Streams on the other hand can store the data for up to 7 days. Which is why is leans towards to Domain 2.0: Storage.

You may use Kinesis Streams if you want to do some custom processing with streaming data. With Kinesis Firehose you are simply ingesting it into S3, Redshift or ElasticSearch.
