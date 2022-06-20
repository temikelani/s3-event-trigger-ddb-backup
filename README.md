# Automating DynamoDB Backups Vis S3 Event Trigggers Using Lambda Functions <a id ='top'></a>

<br><br>

## Summary

- You have a dynamodb table and an s3 bucket.
- And for you want the dynamodb table to be backed up whenever you upload a file to s3.
- You also want an email notification sent when the backup is complete

<br>
<br>
<br>

# Contents

- [Objective](#obj)
- [Steps](#steps)
- [Via Cloud Formation](#0)
- [Resources](#res)
- [go to top](#top)

<br>
<br>

# Objective <a id='obj'></a> ([go to top](#top))

- Automate - using a lambda script - the backup of a ddb table
- Upload a file to s3, and trigger a backup to aws backup
- Send a notification

<br>
<br>
<br>

# Steps <a id='steps'></a> ([go to top](#top))

- Setup Your environment
  - Deploy the [Cloud Formation Template](0-setup/setup-env-cfn.yaml)
  - Upload the [order_data.csv](./0-setup/order_data.csv) to the s3 bucket created

- create an `SNS Topic` and `email subscription`
- Create a `Lambda function` to create a dynamodb table backup
- Add an s3 `s3:ObjectCreated:*` notification trigger to that function with the required lambda permission
- Create a role for the lambda function to
  - create, list and delete DynamoDB backups
  - Publish to SNS topics
  - with the right trust relationship document to allow lambda assume the role
- Upload a file to s3 and test your function
- Update the existing stack with the cloud formation template [solution-cfn.yaml](./1-via-cloud-formation/solution-cfn.yaml) then upload a
  file to S3 to test the backup process.

<br>
<br>
<br>

# Resources <a id='res'></a> ([go to top](#top))

- [Set up scheduled backups for Amazon DynamoDB using AWS Backup](https://aws.amazon.com/blogs/database/set-up-scheduled-backups-for-amazon-dynamodb-using-aws-backup/)
- [Set up scheduled backups using AWS Backup](https://github.com/aws-samples/setup-scheduled-backups-using-aws-backup)
- [Boto3 DynamoDB](https://boto3.amazonaws.com/v1/documentation/api/latest/reference/services/dynamodb.html)
- [A serverless solution to schedule your Amazon DynamoDB On-Demand Backup](https://aws.amazon.com/blogs/database/a-serverless-solution-to-schedule-your-amazon-dynamodb-on-demand-backup)
- [awslabs/dynamodb-backup-scheduler](https://github.com/awslabs/dynamodb-backup-scheduler)
- [Serverless Scheduling with Amazon EventBridge, AWS Lambda, and Amazon DynamoDB](https://aws.amazon.com/blogs/architecture/serverless-scheduling-with-amazon-eventbridge-aws-lambda-and-amazon-dynamodb/)
- [Serverless Scheduling with Amazon EventBridge, AWS Lambda, and Amazon DynamoDB](https://hackernoon.com/automate-your-amazon-dynamodb-on-demand-backup-for-multiple-tables-using-lambda-7sc63zbf)
- [Implement S3 Bucket Lambda triggers in AWS CloudFormation](https://www.itonaut.com/2018/10/03/implement-s3-bucket-lambda-triggers-in-aws-cloudformation/)
- [Scheduling Amazon DynamoDB Backups with Lambda, Python, and Boto3](https://acloudguru.com/blog/engineering/scheduling-amazon-dynamodb-backups-with-lambda-python-and-boto3)
- [Create a Lambda notification in an S3 bucket with CloudFormation](https://stackoverflow.com/questions/38752985/create-a-lambda-notification-in-an-s3-bucket-with-cloudformation)
- [AWS::S3::Bucket LambdaConfiguration](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-properties-s3-bucket-notificationconfig-lambdaconfig.html)
- [Enable Lambda function to an S3 bucket using cloudformation](https://stackoverflow.com/questions/36338890/enable-lambda-function-to-an-s3-bucket-using-cloudformation)
- [Serverless Scheduling with Amazon EventBridge, AWS Lambda, and Amazon DynamoDB](https://docs.aws.amazon.com/AmazonS3/latest/userguide/notification-how-to-event-types-and-destinations.html)
- [Scheduling DynamoDB Backups with Lambda, Python, and Boto3 Raw](https://gist.github.com/mrichman/572990671052f7e08b6f29241d5f2c08#file-lambda_function-py)
- [Implement S3 Bucket Lambda triggers in AWS CloudFormation](https://gist.github.com/LukasMusebrink/30b72b4d739b470fe6f073b9126a8ab6#file-template-yaml)
- [How can I use CloudFormation to create an Amazon S3 notification configuration for Lambda on an existing S3 bucket?](https://aws.amazon.com/premiumsupport/knowledge-center/cloudformation-s3-notification-lambda/)
- [How do I fix the "Unable to validate the following destination configurations" error in AWS CloudFormation?](https://aws.amazon.com/premiumsupport/knowledge-center/unable-validate-destination-s3/)
- [How to Zip Files and Directories in Linux](https://linuxize.com/post/how-to-zip-files-and-directories-in-linux/)
- [Why do I get the error "Configuration is ambiguously defined" when creating an Amazon S3 event notification to trigger my Lambda function?](https://aws.amazon.com/premiumsupport/knowledge-center/lambda-s3-event-configuration-error/)
