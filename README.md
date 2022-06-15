# Automating DynamoDB Backups Vis S3 Event Trigggers Using Lambda Functions <a id ='top'></a>

<br><br>

## Summary
This repo was created as a results of an AWS consultation request from Upwork. 

- The project provides multiple method for ...... coming soon. 


<br>
<br>
<br>

# Contents

- [Objective](#obj)
- [Steps](#steps)
- [Via Cloud Formation](#0)
- [Via Terraform](#1)
- [Via CLI/Bash Script](#2)
- [Via Console](#3)
- [Resources](#res)
- [go to top](#top)

<br>
<br>

# Objective <a id='obj'></a> ([go to top](#top))

## Scenario
  - You have a dynamodb table and an s3 bucket. And for some reason you want the dynamodb table to be backed up whenever you upload a file to s3. You also want an email notification sent when the backup is complete

## Objective

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

- create an `SNS Topic` and and `email subscription`
- Create a `Lambda function`to create a dynamodb table backup
- Add an s3 `s3:ObjectCreated:*` notification trigger to that function with the required lambda permission
- Create a role for the lambda function to
  - create, list and delete DynamoDB backups
  - Publish to SNS topics
  - with the right trust relationship document to allow lambda assume the role
- Upload a file to s3 and test your function

<br>
<br>
<br>

# Via CLoud Formation <a id='0'></a> ([go to top](#top))

Update the existing stack with the cloud formation template [solution-cfn.yaml](./1-via-cloud-formation/solution-cfn.yaml) then upload file to S3 to test the backup process

<details>
<summary> > Click to Expand </summary>
Coming Soon
</details>

<br>
<br>
<br>

# Via Terraform <a id='1'></a> ([go to top](#top))

<details>
<summary> Coming Soon </summary>
Coming Soon
</details>

<br>
<br>
<br>

# Via CLI/Bash Script<a id='2'></a> ([go to top](#top))

<details>
<summary> Click To Expand </summary>

Coming Soon

</details>

<br>
<br>
<br>

# Via Console <a id='3'></a> ([go to top](#top))

<details>
<summary> Coming Soon </summary>

</details>

# Resources <a id='res'></a> ([go to top](#top))

- [Set up scheduled backups for Amazon DynamoDB using AWS Backup](https://aws.amazon.com/blogs/database/set-up-scheduled-backups-for-amazon-dynamodb-using-aws-backup/)
- [Set up scheduled backups using AWS Backup](https://github.com/aws-samples/setup-scheduled-backups-using-aws-backup)

- https://boto3.amazonaws.com/v1/documentation/api/latest/reference/services/dynamodb.html

- https://aws.amazon.com/blogs/database/a-serverless-solution-to-schedule-your-amazon-dynamodb-on-demand-backup/

- https://github.com/awslabs/dynamodb-backup-scheduler

- https://aws.amazon.com/blogs/architecture/serverless-scheduling-with-amazon-eventbridge-aws-lambda-and-amazon-dynamodb/

- https://hackernoon.com/automate-your-amazon-dynamodb-on-demand-backup-for-multiple-tables-using-lambda-7sc63zbf

- https://www.itonaut.com/2018/10/03/implement-s3-bucket-lambda-triggers-in-aws-cloudformation/

- https://acloudguru.com/blog/engineering/scheduling-amazon-dynamodb-backups-with-lambda-python-and-boto3

- https://stackoverflow.com/questions/38752985/create-a-lambda-notification-in-an-s3-bucket-with-cloudformation

- https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-properties-s3-bucket-notificationconfig-lambdaconfig.html

- https://stackoverflow.com/questions/36338890/enable-lambda-function-to-an-s3-bucket-using-cloudformation

- https://docs.aws.amazon.com/AmazonS3/latest/userguide/notification-how-to-event-types-and-destinations.html

- https://gist.github.com/mrichman/572990671052f7e08b6f29241d5f2c08#file-lambda_function-py

- https://gist.github.com/LukasMusebrink/30b72b4d739b470fe6f073b9126a8ab6#file-template-yaml

- https://aws.amazon.com/premiumsupport/knowledge-center/cloudformation-s3-notification-lambda/

- https://aws.amazon.com/premiumsupport/knowledge-center/unable-validate-destination-s3/

- https://linuxize.com/post/how-to-zip-files-and-directories-in-linux/

- https://aws.amazon.com/premiumsupport/knowledge-center/lambda-s3-event-configuration-error/

<br>
<br>
<br>
