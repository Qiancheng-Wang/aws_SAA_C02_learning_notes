Your VPC automatically comes with a default NACL, and by default it allows all inbound and outbound traffic.

You can create custom network ACL, but by default each custom network ACL denies all inbound and outbound traffic until you add rules.

Each subnet in your VPC must be associated with network ACL, and if you don't explicitly associate a subnet with a network ACL, the subnet is automatically associate with the default network ACL.

Block IP addressed with network ACLs not Security Groups.

You can associate a network ACLs with multiple subnets, but a subnet can be associated with only one network ACL at a time. When you associate a network ACL with a subnet, the previous association is removed.

Network ACLs contain a set of rules that is valued in order, starting with the lowest numbered rule.

Network ACLs have separate inbound and outbound rules, and each rule can either allow or deny traffic.

Network ACLs are stateless, responses to allowed inbound traffic are subject to the rules for outbound traffic.
