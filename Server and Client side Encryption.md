You have three mutually exclusive options depending on how you choose to manage the encryption keys:

    1. Use Server-Side Encryption with Amazon S3-Managed Keys (SSE-S3)

    2. Use Server-Side Encryption with AWS KMS-Managed Keys (SSE-KMS)

    3. Use Server-Side Encryption with Customer-Provided Keys (SSE-C)

Client-side encryption is the act of encrypting data before sending it to Amazon S3. To enable client-side encryption, you have the following options:

    1. Use a customer master key (CMK) stored in AWS Key Management Service (AWS KMS).

    2. Use a master key that you store within your application.

If you need server-side encryption for all of the objects that are stored in a bucket, use a bucket policy. For example, the following bucket policy denies permissions to upload an object unless the request includes the `x-amz-server-side-encryption header to request server-side encryption`

However, if you chose to use server-side encryption with customer-provided encryption keys (SSE-C), you must provide encryption key information using the following request headers:

`x-amz-server-side​-encryption​-customer-algorithm`

`x-amz-server-side​-encryption​-customer-key`

`x-amz-server-side​-encryption​-customer-key-MD5`
