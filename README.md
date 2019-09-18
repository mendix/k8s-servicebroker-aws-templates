# AWS Service Broker templates for Mendix

This project contains CloudFormation templates for [AWS Service Broker](https://github.com/awslabs/aws-servicebroker).

This project is a part of the Mendix Private Cloud offering for Kubernetes.

These templates can be used as a reference to provision a database for a Mendix app through an AWS Service Broker [custom catalog](https://github.com/awslabs/aws-servicebroker/tree/master/docs#custom-catalog).

# How to use

1. Upload the `templates` directory to the root of an S3 bucket.
2. Change the AWS Service Broker configuration to use that bucket as the [custom catalog](https://github.com/awslabs/aws-servicebroker/tree/master/docs#custom-catalog).
