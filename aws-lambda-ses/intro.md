## AWS Lambda

Amazon's AWS Lambda is a serverless computing service that allows users to run arbitrary code without provisioning or managing servers. The service can also be scaled up or down depending on the users needs. It can also be invoked by a number of different AWS events in order to create an automated process.

## Amazon Simple Email Service (SES)

Amazon SES is a platform that provides an easy and cost-effective way to send/receive emails using your own email addresses and domains.

SES can be used to send marketing emails such as special offers, transactional emails such as order confirmations, and other types of correspondence such as newsletters automatically through the use of Lambda functions.

In this tutorial you will learn how to send emails using this service together with a Lambda. While receiving emails and processing them automatically does not require much more work, it does require owning a domain. Due to that not being free it has been excluded from this tutorial, instead the function will be invoked through a HTTP request.
