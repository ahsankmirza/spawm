# spawm

Overview: 
- The cloudformation yaml is using S3, and Cloudfront to deliver the SPA. 

Parameters:
- The bucket name is added as a parameter and then referenced within the rest of the file

Resources:
- The first Resource is the S3 Bucket setup with public read with a single document (index.html) for the indexdocument and errordocument
- The second resource is a s3 bucket policy which is being attached to the bucket by (referencing the bucketname). The policy allows public read for the bucket objects for get operations
- The third resource is the cloudfront distro which will be setup with s3 as the origin with custom dns setup. The error code is setup to 404 with a success response code of 200. The default cache behavior is set to default with the SSL option enabled with the default cloudfront certificate
- The outputs are the CF domain, the CF ID, the bucketname and then the s3  website url
