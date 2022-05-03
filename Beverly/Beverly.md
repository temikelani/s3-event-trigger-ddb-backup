# Overview

If you already have the s3 and ddb tables provisioned

- You will have to create/set the s3 Notifications to point to/Trigger the lambda Function upon a creation event
  - s3 notification settings can be found in the Properties section
  <br>
  <br>
  ![](/Beverly/images/event-notification.png)

<br>

- You will need to create an sns email topic for the notifcation

<br>

- You will need to edit the contents of the [lambda function](./Beverly/backup.py)
  ```python
    # environmental variables
  tableName = [enter your ddb table name here]
  snsArn = [enter your sns topic arn here]
  ```
  - You can also edit the contents of the sns messages in the [lambda function](./Beverly/backup.py)



- You will need to create a Lambda Permission for s3 to invoke that function



<br>
<br>
<br>

# References

- [Cli command to create a lambda notification for s3 Bucket](https://awscli.amazonaws.com/v2/documentation/api/latest/reference/s3api/put-bucket-notification-configuration.html)

```
aws s3api put-bucket-notification-configuration \
    --bucket [enter-bucket-name-here] \
    --notification-configuration file://notification.json
```

```
# contents of notifcation.json
{
  "LambdaFunctionConfigurations": [
      {
          "LambdaFunctionArn": "arn:aws:sns:us-west-2:123456789012:s3-notification-topic",
          "Events": [
              "s3:ObjectCreated:*"
          ]
      }
  ]
}

```

- [See the supported s3-notification types](https://docs.aws.amazon.com/AmazonS3/latest/userguide/notification-how-to-event-types-and-destinations.html#supported-notification-event-types)


- Create an email sns topic

```
aws sns create-topic \
    --name my-topic

aws sns list-topics

aws sns subscribe \
    --topic-arn arn:aws:sns:us-west-2:123456789012:my-topic \
    --protocol email \
    --notification-endpoint my-email@example.com
```