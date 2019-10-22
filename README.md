# AWS Service Broker templates for Mendix

This project contains CloudFormation templates for [AWS Service Broker](https://github.com/awslabs/aws-servicebroker).

This project is a part of the Mendix Private Cloud offering for Kubernetes.

These templates can be used as a reference to provision a database for a Mendix app through an AWS Service Broker [custom catalog](https://github.com/awslabs/aws-servicebroker/tree/master/docs#custom-catalog).

The default plans in this repository have the following parameters:

| Service class   | Service Plan | AWS Service        |
|-----------------|--------------|--------------------|
| mendix-database | dev          | AWS RDS PostgreSQL |
| mendix-database | production   | AWS RDS PostgreSQL |
| mendix-storage  | dev          | AWS S3             |
| mendix-storage  | production   | AWS S3             |

# How to use the templates in Service Broker

## Using the plans from this repository

To use service plans from this repository without any changes, configure AWS Service Broker with the following parameters:

| Parameter | Value                       |
|-----------|-----------------------------|
| s3Bucket  | mendix-service-catalog-prod |
| s3Key     | templates/latest            |
| s3Region  | eu-west-1                   |

It might take some time (30 minutes) before the changes are propagated by AWS Service Broker into the Kubernetes Service Catalog.

## Using customized plans

1. Create an S3 bucket with public read and list access.
2. Clone this repository into your local machine by running `git clone https://github.com/mendix/k8s-servicebroker-aws-templates.git`.
3. Customize or replace templates if necessary. Please note that the template should not have any required parameters.
4. Upload the `templates` directory to the root of an S3 bucket.
5. Change the AWS Service Broker configuration to use that bucket as the [custom catalog](https://github.com/awslabs/aws-servicebroker/tree/master/docs#custom-catalog).
