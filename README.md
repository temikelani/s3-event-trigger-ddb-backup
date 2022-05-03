## Automating DDB Backups Vis S3 Event Trigggers Using Lambda Functions <a id ='top'></a>

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

- Automate - using a lambda script - the backup of a ddb table to an aws backup vault. make the automation triggered be triggered by a update/change to the ddb table

- Upload a file to s3, back it up to ddb, and trigger a backup to aws backup

<br>
<br>
<br>

# Steps <a id='steps'></a> ([go to top](#top))

## Setup

## Solution


## Test the Function

<br>
<br>
<br>

# Via CLoud Formation <a id='0'></a> ([go to top](#top))

<details>

</details>

<br>
<br>
<br>

# Via Terraform <a id='1'></a> ([go to top](#top))

<details>

</details>


<br>
<br>
<br>

# Via CLI/Bash Script<a id='2'></a> ([go to top](#top))

<details>

</details>

<br>
<br>
<br>

# Via Console <a id='3'></a> ([go to top](#top))






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



