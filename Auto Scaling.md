A launch configuration is a template that an Auto Scaling group uses to launch EC2 instances. When you create a launch configuration, you specify information for the instances such as the `ID of the Amazon Machine Image (AMI)`, the `instance type`, a `key pair`, one or more `security groups`, and a `block device mapping`. If you've launched an EC2 instance before, you specified the same information in order to launch the instance.

You can specify your launch configuration with `multiple` Auto Scaling groups. However, you can only specify `one` launch configuration for `an Auto Scaling group at a time`, and you `can't modify a launch configuration after you've created it`.

Therefore, if you want to change the launch configuration for an Auto Scaling group, you must create a launch configuration and then update your Auto Scaling group with the new launch configuration.

For this scenario, you have to create a new launch configuration. Remember that you can't modify a launch configuration after you've created it.

## Auto Scaling Policy:

1. Target tracking scaling - Increase or decrease the current capacity of the group based on a `target value for a specific metric`. This is similar to the way that your thermostat maintains the temperature of your home – you select a temperature and the thermostat does the rest.

2. Step scaling - Increase or decrease the current capacity of the group based on `a set of scaling adjustments, known as step adjustments`, that vary based on the size of the alarm breach.

3. Simple scaling - Increase or decrease the current capacity of the group based on a `single scaling adjustment`.

## Determine which instance to close

**Basically: more instances count AZ -> oldest launch configuration -> closest to the next billing hour.**

1. If there are instances in multiple Availability Zones, choose the Availability Zone with the most instances and at least one instance that is not protected from scale in. If there is more than one Availability Zone with this number of instances, choose the Availability Zone with the instances that use the oldest launch configuration.

2. Determine which unprotected instances in the selected Availability Zone use the oldest launch configuration. If there is one such instance, terminate it.

3. If there are multiple instances to terminate based on the above criteria, determine which unprotected instances are closest to the next billing hour. (This helps you maximize the use of your EC2 instances and manage your Amazon EC2 usage costs.) If there is one such instance, terminate it.

4. If there is more than one unprotected instance closest to the next billing hour, choose one of these instances at random.
