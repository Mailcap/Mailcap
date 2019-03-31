# Mailcap API documentation

This is Mailcap API documentation. We use the API for our own web frontend and you're free to use it for your own projects and hacks.

If you find an error in the documentation, file an issue or send a pull request.

## Format

All data is returned in JSON format. 

## Authentication

Part of the API requires authentication. Easiest way to test the API is to open GET endpoint in Chrome with [JSONView](https://chrome.google.com/webstore/detail/jsonview/chklaanhfefbnpoihckbnefhakgolnmc) extension installed.

Supported authentication:

- Browser session
- API Token

[Read more about authentication](https://github.com/Mailcap/Mailcap/tree/master/API/v1#authentication)

## Interacting with the API

Mailcap API is based on REST principles

- create → POST   /api/v1/inboxes
- read → GET   /api/v1/inboxes[/id]
- update → PATCH /api/v1/inboxes/id
- delete → DELETE   /api/v1/inboxes/id

[Error codes](https://github.com/Mailcap/Mailcap/tree/master/API/v1##error-codes)

### User

- [**<code>GET</code> /api/v1/user**](https://github.com/Mailcap/Mailcap/tree/master/API/v1#user)
- [**<code>GET</code> /api/v1/user/reset_token**](https://github.com/Mailcap/Mailcap/tree/master/API/v1#reset-user-api-token)

### Inbox

- [**<code>GET</code> /api/v1/inboxes**](https://github.com/Mailcap/Mailcap/tree/master/API/v1#get-list-of-inboxes)
- [**<code>POST</code> /api/v1/inboxes**](https://github.com/Mailcap/Mailcap/tree/master/API/v1#create-inbox)
- [**<code>GET</code> /api/v1/inboxes/stats**](https://github.com/Mailcap/Mailcap/tree/master/API/v1#get-stats-of-inboxes)
- [**<code>GET</code> /api/v1/inboxes/messages**](https://github.com/Mailcap/Mailcap/tree/master/API/v1#get-messages-from-all-inboxes)
- [**<code>GET</code> /api/v1/inboxes/:inbox_id**](https://github.com/Mailcap/Mailcap/tree/master/API/v1#get-inbox)
- [**<code>PATCH</code> /api/v1/inboxes/:inbox_id**](https://github.com/Mailcap/Mailcap/tree/master/API/v1#update-inbox)
- [**<code>DELETE</code> /api/v1/inboxes/:inbox_id**](https://github.com/Mailcap/Mailcap/tree/master/API/v1#delete-inbox)
- [**<code>PATCH</code> /api/v1/inboxes/:inbox_id/clean**](https://github.com/Mailcap/Mailcap/tree/master/API/v1#clean-all-messages-emails-from-inbox)
- [**<code>PATCH</code> /api/v1/inboxes/:inbox_id/all_read**](https://github.com/Mailcap/Mailcap/tree/master/API/v1#mark-all-messages-emails-as-read)
- [**<code>PATCH</code> /api/v1/inboxes/:inbox_id/reset_credentials**](https://github.com/Mailcap/Mailcap/tree/master/API/v1#reset-inbox-credentials)

### Message

- [**<code>GET</code> /api/v1/inboxes/:inbox_id/messages**](https://github.com/Mailcap/Mailcap/tree/master/API/v1#get-messages-from-inbox)
- [**<code>GET</code> /api/v1/inboxes/:inbox_id/messages?search=**](https://github.com/Mailcap/Mailcap/tree/master/API/v1#find-messages)
- [**<code>GET</code> /api/v1/inboxes/:inbox_id/messages/:message_id**](https://github.com/Mailcap/Mailcap/tree/master/API/v1#get-one-message-from-inbox)
- [**<code>PATCH</code> /api/v1/inboxes/:inbox_id/messages/:message_id**](https://github.com/Mailcap/Mailcap/tree/master/API/v1#update-message-attributes-right-now-available-only-read-attribute-for-modification)
- [**<code>DELETE</code> /api/v1/inboxes/:inbox_id/messages/:message_id**](https://github.com/Mailcap/Mailcap/tree/master/API/v1#delete-message)
- [**<code>GET</code> /api/v1/inboxes/:inbox_id/messages/:message_id/urls**](https://github.com/Mailcap/Mailcap/tree/master/API/v1#message-html)
- [**<code>GET</code> /api/v1/inboxes/:inbox_id/messages/:message_id/mail.html**](https://github.com/Mailcap/Mailcap/tree/master/API/v1#message-html)
- [**<code>GET</code> /api/v1/inboxes/:inbox_id/messages/:message_id/body.txt**](https://github.com/Mailcap/Mailcap/tree/master/API/v1#message-text)
- [**<code>GET</code> /api/v1/inboxes/:inbox_id/messages/:message_id/raw**](https://github.com/Mailcap/Mailcap/tree/master/API/v1#message-raw)


### Attachment

- [**<code>GET</code> /api/v1/inboxes/:inbox_id/messages/:message_id/attachments/:file_number/download**](https://github.com/Mailcap/Mailcap/tree/master/API/v1#download)

## Contribution


