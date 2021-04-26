## Creating the Lambda Function

Navigate to the `Lambda` service and create a new function from scratch with a name of your choice (Eg. `sendEmailLambda`) and assign it the permission that we created in step 2 (`LambdaEmail`).

Next we'll write the following code and click deploy.

<pre class="javascript">
var aws = require("aws-sdk");
var ses = new aws.SES({ region: "us-west-2" });
exports.handler = async function (event) {
  var params = {
    Destination: {
      ToAddresses: ["sfkwww@gmail.com"],
    },
    Message: {
      Body: {
        Text: { Data: "No worries mate, be careful next time" },
      },

      Subject: { Data: "Re: Help, From: Kumar" },
    },
    Source: "swill.devops@gmail.com",
  };

  return ses.sendEmail(params).promise()
};
</pre>

The imported `aws-sdk` allows us to use Javascript API for AWS services. In this particular function we use it to access the SES service.
