# Summary
Integration with slack can be used to send alerts to users and channels to notify when certain events are triggered.

# API AutoFlow Version:
Configuration config.json was created using AutoFlow version __0.2.5__

# Need help?
Is you have questions about this example, feel free to post your question on the community "Ask Questions" website.

[Ask Questions](https://interactor.com/autoflow/questions){: .btn}

## Step 1. Create flow
* Create an HTTP Server
* Create an endpoint
  * NOTE: under properties the method must be POST
* From the right panel, press Action tab -> communication, Drag and drop HTTP-Request to the end of the flow
* From the right panel, press Action tab -> data, Drag and drop Set to the end of the flow

![Image](https://github.com/API-AutoFlow/slack-webhook/blob/master/img/1.png)

## Step 2. Setup Slack request body
Slack takes in HTTP request body as below

```
{
    "text": "Message content"
}
```

Use Data/Set action to create the object.

## Step 3. Slack API Call
### Communication/HTTP-request
#### Properties:
> * _url_: NOTE: Paste the slack webhook
> * _Method_: POST
> * _Body_: Contents of what is being posted to slack. NOTE: May need to specify the content type as application json.  { “Content-Type”: “Application/JSON” }
> * _Header_: blank
> * _Query_: blank
> * _Timeout_: Default

#### Output:
> * _Output-location_: Drag and drop the response body from right data panel
![Image](https://github.com/API-AutoFlow/slack-webhook/blob/master/img/2.gif)


## Step 4. Test and Send Messages to your workspace

## Using Talent API Tester:
Select Method Post and Paste your slack http server. NOTE: Yours may differ
![Image](https://github.com/API-AutoFlow/slack-webhook/blob/master/img/4.gif)

or use Postman
![Image](https://github.com/API-AutoFlow/slack-webhook/blob/master/img/5.png)

In the HTTP Request Header, insert the message you want to send. For example

> Hello World!

## Configuring Slack api webhook

For Additional help on sending messages Slack webhooks:
https://api.slack.com/messaging/webhooks

* Navigate to api.slack.com
* Once logged in click on Your Apps on the right end of the navigation bar
* Select Create New App
  * Create the application name and select which workspace this app will belong too
* Select basic information underneath the settings.  Select add features and functionality.  From here you can add additional functionality but for this example we just are using incoming webhooks.
* After selecting and activating incoming webhooks. Scroll to the bottom and select add new webhook to workspace. Select which channel to post to and allow.
* Copy JUST the URL from the sample. NOTE: Your webhook will be unique
* Paste the slack webhook on the url line under properties from the communication/http-request action
![Image](https://github.com/API-AutoFlow/slack-webhook/blob/master/img/3.png)
