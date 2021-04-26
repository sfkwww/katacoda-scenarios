In this project we will be using the AWS Lambda service to generate our email. In order to do that we'll need to give it the correct permissions.

## Configuring IAM Permissions

First let's create a policy document which specifies the permissions our lambda function needs.

Navigate to the `IAM Service`, click on the `Policies` tab and press `Create policy`.

Using the JSON Editor copy and paste the following policy:

<pre class="file" data-target="copy">
{
    "Version": "2012-10-17",
    "Statement": [
         {
             "Effect": "Allow",
             "Action": [
                 "ses:SendEmail",
                 "ses:SendRawEmail"
             ],
             "Resource": "*"
         }
     ]
}
</pre>

Continue with the rest of the steps and name the policy `WriteEmails`.

>For more information about the type of access that can be given/restricted in AWS SES see the [Developer Guide](https://docs.aws.amazon.com/ses/latest/DeveloperGuide/control-user-access.html)

Next we need to attach this policy to a role. Simply click on the `Roles` tab and create a new role for `Lambda` with the `WriteEmails` permission we just created. Name it `LambdaEmail` or something you'll remember for the next steps.
