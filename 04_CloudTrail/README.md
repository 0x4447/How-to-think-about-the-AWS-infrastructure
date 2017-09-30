# CloudTrail

This tool is a very nice debugging tool. Normally SysAdmins will turn this feature on to see what is happening in the AWS infrastructure, since you can see, who loved in, who created a EC2 instance, who deleted a RDS database. Hence the name Trail. 

Another benefit of this logging is that API calls from outside will be logged here, making much easier to debug integrations such as GitHub pushing a notification to CodeDeploy. And for example you might see that the credentials are wrong, etc. 

# Be aware of the bad description

When you'll create a new CloudTrail there will be a section called `Data events` and wehn you are ging to read it you'll think that the CloudTrail applyes only to S3 and not to everything. A fristrating mistake that I did. But in reality basically this is how to think of it...

CloudTrail will log evrything but S3 events, and if you would like to alos include S3 events, you cane do it in the `Data events`.

# How to enable CloudTrail

- Go to S3 and create a new Bucket where all the logs are goign to end up
- Go to the CloudTrail section
- Click Create Trail
- Give it a name
- Apply trail to all regions: keept it yes
- Management events: keept it to All
- In the Data Events section select: Select all S3 buckets in your account
- In the Storage Location, select No for Create a new S3 bucket
- From the drop down menu select the bucket that you created previously
- Click Create.

Aditional details can be found [here](http://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-create-a-trail-using-the-console-first-time.html#creating-a-trail-in-the-console)

The logs should start showign up within 15 minutes.