AWS Global Accelerator and Amazon CloudFront are separate services that use the AWS global network and its edge locations around the world.

CloudFront improves performance for both `cacheable content` (such as images and videos) and `dynamic content` (such as API acceleration and dynamic site delivery).

Global Accelerator improves performance for a wide range of applications over TCP or UDP by proxying packets at the edge to applications running in one or more AWS Regions. Global Accelerator is a good fit for `non-HTTP use cases`, such as gaming (UDP), IoT (MQTT), or Voice over IP, as well as for HTTP use cases that specifically require static IP addresses or deterministic, fast regional failover. Both services integrate with AWS Shield for DDoS protection.
