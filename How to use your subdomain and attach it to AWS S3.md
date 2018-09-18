Just read here https://stackoverflow.com/questions/18765934/how-appoint-a-subdomain-for-a-s3-bucket

Basically just create an AWS S3 bucket similar with your planned subdomain for store static content, let say s3static.yourdomain.com

Then create the subdomain s3static.yourdomain.com on your domain DNS manager and point it to <bucket-name>.s3.amazonaws.com. as CNAME record. In this sample like this `s3static.yourdomain.com.s3.amazonaws.com.`

That's it.

The full instructions are available here:

http://docs.aws.amazon.com/AmazonS3/latest/dev/VirtualHosting.html
