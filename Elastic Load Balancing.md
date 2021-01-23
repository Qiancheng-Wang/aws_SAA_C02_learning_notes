If you need flexible application management and TLS termination then we recommend that you use Application Load Balancer.

If extreme performance and static IP is needed for your application then we recommend that you use Network Load Balancer.

If your application is built within the EC2 Classic network then you should use Classic Load Balancer.

An Application Load Balancer functions at the `application layer`, the seventh layer of the Open Systems Interconnection (OSI) model. After the load balancer receives a request, it evaluates the listener rules in priority order to determine which rule to apply, and then selects a target from the target group for the rule action. You can configure listener rules to route requests to different target groups based on the content of the application traffic. Routing is performed independently for each target group, even when a target is registered with multiple target groups.

Application Load Balancers support `path-based routing`, `host-based routing` and support for `containerized applications`.

## Route Name Record Alias types:

To route domain traffic to an ELB load balancer, use Amazon Route 53 to create an alias record that points to your load balancer. An alias record is a Route 53 extension to DNS. It's similar to a CNAME record, but you can create an alias record both for the root domain, such as tutorialsdojo.com, and for subdomains, such as portal.tutorialsdojo.com. (You can create **CNAME records only for subdomains**.)

To enable `IPv6 resolution`, you would need to create a second resource record, tutorialsdojo.com `ALIAS AAAA` -> myelb.us-west-2.elb.amazonnaws.com, this is assuming your Elastic Load Balancer has IPv6 support.
