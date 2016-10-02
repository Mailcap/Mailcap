# Authentication

Mailcap API requires authentication for some endpoints. You can use one of the following authentication methods.

## Browser session

You can access Mailcap API when you're logged into Mailcap using regular browser session. Easiest way to test the API is to open GET endpoint in Chrome with [JSONView](https://chrome.google.com/webstore/detail/jsonview/chklaanhfefbnpoihckbnefhakgolnmc) extension installed.

## Token Auth

You can authenticate with API token. Exists several way to do this:

- Send a HTTP header ```Authorization: Bearer <token>```
- Send a parameter ```access_token=<api_token>```.

Where <api_token> is your API token.

_Example:_
```
     POST /api/v1/inboxes HTTP/1.1
     Host: mailcap.io
     Content-Type: application/x-www-form-urlencoded

     access_token=b7da7d7b7d9a7d5b4da
```
_Example:_
```
     GET /api/v1/inboxes?access_token=b7da7d7b7d9a7d5b4da HTTP/1.1
     Host: mailcap.io
```
_Example:_
```
     GET /api/v1/inboxes HTTP/1.1
     Host: mailcap.io
     Authorization: Bearer b7da7d7b7d9a7d5b4da
```
[more info](http://tools.ietf.org/html/rfc6750)

Your API token you can find on [profile page](https://mailcap.io/setting) in Mailcap application.

