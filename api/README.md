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

- [**<code>GET</code> /api/v1/user/reset_token**](https://github.com/Mailcap/API/blob/master/v1/user.md#reset_token)


### Inbox

- [**<code>GET</code> /api/v1/inboxes**](https://github.com/Mailcap/API/blob/master/v1/inbox.md#inboxes)
- [**<code>POST</code> /api/v1/inboxes**](https://github.com/Mailcap/API/blob/master/v1/inbox.md#inbox_create)
- [**<code>GET</code> /api/v1/inboxes/:inbox_id**](https://github.com/Mailcap/API/blob/master/v1/inbox.md#inbox)
- [**<code>PATCH</code> /api/v1/inboxes/:inbox_id**](https://github.com/Mailcap/API/blob/master/v1/inbox.md#patch_inbox)
- [**<code>DELETE</code> /api/v1/inboxes/:inbox_id**](https://github.com/Mailcap/API/blob/master/v1/inbox.md#delte_inbox)
- [**<code>PATCH</code> /api/v1/inboxes/:inbox_id/clean**](https://github.com/Mailcap/API/blob/master/v1/inbox.md#clear)
- [**<code>PATCH</code> /api/v1/inboxes/:inbox_id/all_read**](https://github.com/Mailcap/API/blob/master/v1/inbox.md#all_read)
- [**<code>PATCH</code> /api/v1/inboxes/:inbox_id/reset_credentials**](https://github.com/Mailcap/API/blob/master/v1/inbox.md#reset_credentials)


### Message

- [**<code>GET</code> /api/v1/inboxes/:inbox_id/messages**](https://github.com/Mailcap/API/blob/master/v1/message.md#message)
- [**<code>GET</code> /api/v1/inboxes/:inbox_id/messages?search=**](https://github.com/Mailcap/API/blob/master/v1/message.md#find-messages)
- [**<code>GET</code> /api/v1/inboxes/:inbox_id/messages/:message_id**](https://github.com/Mailcap/API/blob/master/v1/message.md#get-one-message-from-inbox)
- [**<code>PATCH</code> /api/v1/inboxes/:inbox_id/messages/:message_id**](https://github.com/Mailcap/API/blob/master/v1/message.md#update-message-attributes-right-now-available-only-read-attribute-for-modification)
- [**<code>DELETE</code> /api/v1/inboxes/:inbox_id/messages/:message_id**](https://github.com/Mailcap/API/blob/master/v1/message.md#delete-message)
- [**<code>GET</code> /api/v1/inboxes/:inbox_id/messages/:message_id/mail.html**](https://github.com/Mailcap/API/blob/master/v1/message.md#message_html)
- [**<code>GET</code> /api/v1/inboxes/:inbox_id/messages/:message_id/body.txt**](https://github.com/Mailcap/API/blob/master/v1/message.md#message_text)
- [**<code>GET</code> /api/v1/inboxes/:inbox_id/messages/:message_id/raw**](https://github.com/Mailcap/API/blob/master/v1/message.md#message_raw)


### Attachment

- [**<code>GET</code> /api/v1/inboxes/:inbox_id/messages/:message_id/attachments/:file_number/download**](https://github.com/Mailcap/API/blob/master/v1/attachment.md)

## Contribution

