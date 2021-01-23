## NAT instances

When creating a NAT instance, disabled Source/Destination Check on the instance.

NAT instances must be in a public subnet.

There must be a route out of the private subnet to the NAT instance, in order for this to work.

The amount of traffic that NAT instances can support depends on the instance size. If you bottlenecking, increase the instance size.

NAT instances are always behind security group.

## NAT Gateways

Redundant inside the Availability Zone.

Starts at 5Gbps and scales currently to 45Gbps.

NAT Gateways are not associated with security groups.

NAT Gateways are automatically assigned a public ip address.

Only need to update the route table for the NAT Gateways.

No need to disable Source/Destination Checks.
