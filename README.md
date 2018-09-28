# aws-cloudwatch-logs-forwarder-example
Simple example for a working cross-account solution for AWS CloudWatch forwarding via Kinesis.
This example assumes two different AWS accounts and the usage of more than one AWS region.

The example solution allows you to deliver AWS Cloudwatch logs in region A and Account Y to be delivered to region B in account Z. However, it will work just fine within one region and one account.

The logs will be delivered to an S3 bucket using AWS Kinesis Data Firehose. AWS Kinesis Data Firehose has other possible targets, such as AWS ElastivSearch.

## How to use
1. In the target account, prepare the logs delivery using using the AWS CloudFormation template `logs-delivery.yaml`
1. In the target account, prepare the receiver `logs-receiver.yaml`. The receiver can be in another region than the logs delivery, but must be in the same region as the log producer.
1. In the source account, create a dummy logs producer using the template `logs-producer.yaml`. Outside of this example, this might be your application.
1. In the source account, create the logs forwarder using the template `logs-sender.yaml`. It must be in the same region as the logs producer.
