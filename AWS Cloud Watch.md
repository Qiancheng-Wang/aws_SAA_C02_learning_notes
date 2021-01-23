## Cloud Watch Monitoring Metrics

`CPU Utilization` identifies the processing power required to run an application upon a selected instance.

`Network Utilization` identifies the volume of incoming and outgoing network traffic to a single instance.

`Disk Reads metric` is used to determine the volume of the data the application reads from the hard disk of the instance. This can be used to determine the speed of the application.

However, there are certain metrics that are not readily available in CloudWatch such as `memory utilization`, `disk space utilization`, and many others which can be collected by setting up a custom metric.

You need to prepare a custom metric using `**CloudWatch Monitoring Scripts**` which is written in Perl.

You can also install `**CloudWatch Agent**` to collect more system-level metrics from Amazon EC2 instances. Here's the list of custom metrics that you can set up:

- Memory utilization
- Disk swap utilization
- Disk space utilization
- Page file utilization
- Log collection

## Cloud Watch Alarms Actions:

You can create alarms that automatically `stop`, `terminate`, `reboot`, or `recover` your EC2 instances using Amazon CloudWatch `alarm actions`.

You can use the stop or terminate actions to help you save money when you no longer need an instance to be running.

You can use the reboot and recover actions to automatically reboot those instances or recover them onto new hardware `if a system impairment occurs`.

## CloudWatch Events Rule

You can set up a CloudWatch Events rule that runs an Amazon ECS task whenever a file is uploaded to a certain Amazon S3 bucket using the Amazon S3 PUT operation. You can also declare a reduced number of ECS tasks whenever a file is deleted on the S3 bucket using the DELETE operation.
