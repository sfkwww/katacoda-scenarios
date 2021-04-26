## Creating an HTTP Endpoint

Finally let's create a trigger for our lambda. Simply click on `Add Trigger` from the lambda overview and select `API Gateway`. Then create a new `HTTP API` with security `Open` and press `Add`.

![Lambda Overview](assets/Lambda-Overview.png)

Now whenever this http request is called our lambda function will run and send an email. Try it out by copying the endpoint and pasting it in the browser:

![Endpoint Location](assets/Endpoint-Info.png)