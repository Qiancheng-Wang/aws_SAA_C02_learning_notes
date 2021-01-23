![EC2 instance lifecycle](assets/instance_lifecycle.png)

Below are the valid EC2 lifecycle instance states:

pending - The instance is preparing to enter the running state. An instance enters the pending state when it launches for the first time, or when it is restarted after being in the stopped state.

running - The instance is running and ready for use.

stopping - The instance is preparing to be stopped.
Take note that you will `not billed if it is preparing to stop` however, you will still `be billed if it is just preparing to hibernate`.

stopped - The instance is shut down and cannot be used. The instance can be restarted at any time.

shutting-down - The instance is preparing to be terminated.

terminated - The instance has been permanently deleted and cannot be restarted. Take note that `Reserved Instances that applied to terminated instances are still billed until the end of their term according to their payment option`.

## Spot instance state setting.

You can choose to have your Spot instances terminated, stopped, or hibernated upon interruption. Stop and hibernate options are available for persistent Spot requests and Spot Fleets with the maintain option enabled.

By default, your instances are `terminated` hence, the correct answer is the option that says: The instance will be terminated.
