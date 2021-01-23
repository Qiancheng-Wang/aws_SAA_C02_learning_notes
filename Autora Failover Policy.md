If you have an `Amazon Aurora Replica` in the same or a different Availability Zone, when failing over:

    Amazon Aurora flips the **canonical name record (CNAME)** for your DB Instance to point at the healthy replica, which in turn is promoted to become the new primary. Start-to-finish, failover typically completes within 30 seconds.

If you are running `Aurora Serverless` and the DB instance or AZ become unavailable:

    Aurora will automatically recreate the DB instance in a different AZ.

If you do `not` have an `Amazon Aurora Replica` (i.e. single instance) and are `not running Aurora Serverless`:

    Aurora will attempt to **create a new DB Instance in the same Availability Zone as the original instance**. This replacement of the original instance is done on a best-effort basis and may not succeed, for example, if there is an issue that is broadly affecting the Availability Zone.
