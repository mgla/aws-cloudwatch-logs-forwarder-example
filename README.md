# aws-cloudwatch-logs-forwarder-example
Simple example for a working cross-account solution for AWS CloudWatch forwarding via Kinesis.
This example assumes two different AWS accounts and the usage of more than one AWS region.

The example solution allows you to deliver AWS Cloudwatch logs in region A and Account Y to be delivered to region B in account Z. However, it will work just fine within one region and one account.

The logs will be delivered to an S3 bucket using AWS Kinesis Data Firehose. AWS Kinesis Data Firehose has other possible targets, such as AWS ElastivSearch.


