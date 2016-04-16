# facebook-messenger-bots
omg much excite w0w


So.. I'll try to summarize briefly here and then add more details later.
It's probably better to get overview and key points here but to follow Facebook documentation to be honest.

Setup concepts/steps:
* We have a custom server somewhere that has webhook API up for GET and POST.
* We make facebook web app, make a facebook page
* open up the messenger tab, create webhooks by checking all boxes and typing in the server webhook api url and the verify token
* the verify token should match the same verify token that you check against in the webhook GET api endpoint
* clicking the 'verify and save' button should initiate the GET request to webhook api, verifying the server
* get the page access token
* connect the fb app to the fb page by sending a curl request:
* `curl -ik -X POST "https://graph.facebook.com/v2.6/me/subscribed_apps?access_token=<token>"`
* after this is setup, all messages sent to the facebook page will redirect to the webhook POST api on your custom server
* in the POST api, react accordingly and add AI if you wish
