# Hosting a static website on S3 bucket and much more!

1. Logged in to AWS management console as root user
2. Created a S3 (Simple Storage Service) bucket by enabling ACL (Access Control List) for making the objects publicly visible
3. Uploaded the HTML and CSS files as objects into the bucket
4. Configured the static website hosting on the bucket by enabling it
5. Error occurred because, only the bucket is made public and not objects. So, objects are made publicly accessible too
6. Assigned a pre-signed URL for the objects to share them for particular users for a particular time. This removes the task of changing the overall access settings of the bucket and objects
7. Added a bucket policy to secure the bucket and its objects from deletion
8. Enabled bucket versioning. This helps in creating versions of buckets when the objects inside it are changed.
9. Using Route53 to host the website on own domain. Route53 helps in creating a DNS for the user and host the website on it. It also routes the traffic from outside into our domain. Since, I'm on free tier, I didn't create one 😅
