## Creating the Lambda Function

Navigate to the `Lambda` service and create a new function from scratch with Node.js runtime. Give it a name of your choice (Eg. `sendEmailLambda`) and assign it the permission that we created in step 2 (`LambdaEmail`) by pressing `Change default execution role` and then pick `Use an existing role`.

Next we'll write the following code and click deploy. (Be sure to change the emails to the ones you have used)

<pre class="file" data-target="clipboard">
var aws = require("aws-sdk");
var ses = new aws.SES({ region: "us-west-2" });
exports.handler = async function (event) {
  var params = {
    Destination: {
      ToAddresses: ["destination@email.com"],
    },
    Message: {
      Body: {
        Text: { Data: "No worries mate, be careful next time" },
      },

      Subject: { Data: "Re: Help, From: Kumar" },
    },
    Source: "source@email.com",
  };

  return ses.sendEmail(params).promise()
};
</pre>

The imported `aws-sdk` allows us to use Javascript API for AWS services. In this particular function we use it to access the SES service.
