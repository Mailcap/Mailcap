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

[Read more about authentication](https://github.com/Mailcap/API/blob/master/v1/authentication.md)

## Interacting with the API

Mailcap API is based on REST principles

- create → POST   /api/v1/inboxes
- read → GET   /api/v1/inboxes[/id]
- update → PATCH /api/v1/inboxes/id
- delete → DELETE   /api/v1/inboxes/id

[Error codes](https://github.com/Mailcap/API/blob/master/v1/error_codes.md)

### User

- [**<code>GET</code> /api/v1/user/reset_token**](https://github.com/Mailcap/Mailcap/tree/master/API/v1#reset_token)


### Inbox

- [**<code>GET</code> /api/v1/inboxes**](https://github.com/Mailcap/Mailcap/tree/master/API/v1#inboxes)
- [**<code>POST</code> /api/v1/inboxes**](https://github.com/Mailcap/Mailcap/tree/master/API/v1#inboxes-create)
- [**<code>GET</code> /api/v1/inboxes/stats**](https://github.com/Mailcap/Mailcap/tree/master/API/v1#inboxes-stats)
- [**<code>GET</code> /api/v1/inboxes/messages**](https://github.com/Mailcap/Mailcap/tree/master/API/v1#inboxes-messages)
- [**<code>GET</code> /api/v1/inboxes/messages?search=**](https://github.com/Mailcap/Mailcap/tree/master/API/v1#inboxes-find-messages)
- [**<code>GET</code> /api/v1/inboxes/:inbox_id**](https://github.com/Mailcap/Mailcap/tree/master/API/v1#inbox)
- [**<code>PATCH</code> /api/v1/inboxes/:inbox_id**](https://github.com/Mailcap/Mailcap/tree/master/API/v1#inbox-edit)
- [**<code>DELETE</code> /api/v1/inboxes/:inbox_id**](https://github.com/Mailcap/Mailcap/tree/master/API/v1#inbox-delete)
- [**<code>PATCH</code> /api/v1/inboxes/:inbox_id/clean**](https://github.com/Mailcap/Mailcap/tree/master/API/v1#inbox-clear)
- [**<code>PATCH</code> /api/v1/inboxes/:inbox_id/all_read**](https://github.com/Mailcap/Mailcap/tree/master/API/v1#inbox-all-read)
- [**<code>PATCH</code> /api/v1/inboxes/:inbox_id/reset_credentials**](https://github.com/Mailcap/Mailcap/tree/master/API/v1#inbox-reset-credentials)


### Message

- [**<code>GET</code> /api/v1/inboxes/:inbox_id/messages**](https://github.com/Mailcap/Mailcap/tree/master/API/v1#messages)
- [**<code>GET</code> /api/v1/inboxes/:inbox_id/messages?search=**](https://github.com/Mailcap/Mailcap/tree/master/API/v1#messages-find)
- [**<code>GET</code> /api/v1/inboxes/:inbox_id/messages/:message_id**](https://github.com/Mailcap/Mailcap/tree/master/API/v1#message)
- [**<code>PATCH</code> /api/v1/inboxes/:inbox_id/messages/:message_id**](https://github.com/Mailcap/Mailcap/tree/master/API/v1#message-update)
- [**<code>DELETE</code> /api/v1/inboxes/:inbox_id/messages/:message_id**](https://github.com/Mailcap/Mailcap/tree/master/API/v1#message-delete)
- [**<code>GET</code> /api/v1/inboxes/:inbox_id/messages/:message_id/mail.html**](https://github.com/Mailcap/Mailcap/tree/master/API/v1#message-html)
- [**<code>GET</code> /api/v1/inboxes/:inbox_id/messages/:message_id/body.txt**](https://github.com/Mailcap/Mailcap/tree/master/API/v1#message-text)
- [**<code>GET</code> /api/v1/inboxes/:inbox_id/messages/:message_id/raw**](https://github.com/Mailcap/Mailcap/tree/master/API/v1#message-raw)


### Attachment

- [**<code>GET</code> /api/v1/inboxes/:inbox_id/messages/:message_id/attachments/:file_number/download**](https://github.com/Mailcap/Mailcap/tree/master/API/v1#download)

## Contribution


