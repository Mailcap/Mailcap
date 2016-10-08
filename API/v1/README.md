# API

## Authentication

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

# Inbox

Describes <code>Inbox</code> object.

## Get list of inboxes

    GET /api/v1/inboxes

### Parameters

- _None_

### Errors

- _None_

### Example

**Request**

    GET /api/v1/inboxes

**Return**

    [
        {
            messages: [ ],
            createdAt: "2015-03-11T21:38:36.378Z",
            name: "777",
            password: "a3c1ecb48d78a4",
            timestamp: "1426109916378",
            updatedAt: "2015-03-11T22:15:17.105Z",
            username: "7a182d791c60772e",
            id: "5500b5dc589560c25a4a7eb2",
            messages_count: 0,
            messages_unread_count: 0,
            messages_last_sent: null
        },
        {
            messages: [ ],
            name: "test1",
            username: "8eb635a4bc08e0ab",
            password: "9fc9e3f356c44e",
            timestamp: "1425828736810",
            createdAt: "2015-03-08T15:32:16.810Z",
            updatedAt: "2015-03-11T22:15:25.388Z",
            id: "54fc6b80313cc11e78f9b35b",
            messages_count: 0,
            messages_unread_count: 0,
            messages_last_sent: null
        },
        {
            messages: [ ],
            createdAt: "2015-03-07T07:16:12.224Z",
            name: "test",
            password: "b809c2fc8801e7",
            timestamp: "1425712572224",
            updatedAt: "2015-03-12T21:14:43.243Z",
            username: "257b4a0177ea9591",
            id: "54faa5bcdc64b8b915a369a6",
            messages_count: 8,
            messages_unread_count: 2,
            messages_last_sent: "2015-03-19T18:53:03.014Z"
        }
    ]

## Get stats of inboxes

    GET /api/v1/stats

### Parameters

- _None_

### Errors

- _None_

### Example

**Request**

    GET /api/v1/stats

**Return**

     {
          "messages_count": 6778,
          "messages_unread_count": 6065,
          "messages_last_sent": "2016-10-08T10:34:43.164Z",
          "messages_read_count": 713
     }

## Create inbox

    POST /api/v1/inboxes

### Parameters

- _None_

### Errors

- _None_

### Example

**Request**

    POST /api/v1/inboxes
    Content-Type: application/json
    {
        "name":"test1"
    }

**Return**

    {
        "name": "111",
        "username": "3f5758936e04a3a9",
        "password": "a8dc96cca11735",
        "timestamp": "1426962620538",
        "createdAt": "2015-03-21T18:30:20.538Z",
        "updatedAt": "2015-03-21T18:30:20.539Z",
        "id": "550db8bc906974d8490811b8",
        "messages_count": 0,
        "messages_unread_count": 0,
        "messages_last_sent": null
    }


## Get inbox

    GET /api/v1/inboxes/:inbox_id

### Parameters

<table>
  <tr>
    <td><b>Parameter</b></td>
    <td><b>Description</b></td>
    <td><b>Details</b></td>
  </tr>
  <tr>
    <td><b>inbox_id</b></td>
    <td>inbox ID (identifier)</td>
    <td>required</td>
  </tr>
</table>


### Errors

- <code>404</code> - Inbox not found

### Example
**Request**

    GET /api/v1/inboxes/5500b5dc589560c25a4a7eb2

**Return**

    {
      messages: [ ],
      createdAt: "2015-03-11T21:38:36.378Z",
      name: "777",
      password: "a3c1ecb48d78a4",
      timestamp: "1426109916378",
      updatedAt: "2015-03-11T22:15:17.105Z",
      username: "7a182d791c60772e",
      id: "5500b5dc589560c25a4a7eb2",
      messages_count: 0,
      messages_unread_count: 0,
      messages_last_sent: null
    }


## Update inbox

    PATCH /api/v1/inboxes/:inbox_id

### Parameters

<table>
  <tr>
    <td><b>Parameter</b></td>
    <td><b>Description</b></td>
    <td><b>Details</b></td>
  </tr>
  <tr>
    <td><b>inbox_id</b></td>
    <td>inbox ID (identifier)</td>
    <td>required</td>
  </tr>
</table>


### Errors

- <code>404</code> - Inbox not found

### Example
**Request**

    PATCH /api/v1/inboxes/5500b5dc589560c25a4a7eb2
    Content-Type: application/json
    {
        "name":"test1"
    }

**Return**

    {
        "createdAt": "2015-03-08T15:32:16.810Z",
        "name": "test1",
        "password": "9fc9e3f356c44e",
        "timestamp": "1425828736810",
        "updatedAt": "2015-03-21T18:16:32.792Z",
        "username": "8eb635a4bc08e0ab",
        "id": "5500b5dc589560c25a4a7eb2"
    }


## Delete inbox

    DELETE /api/v1/inboxes/:inbox_id

### Parameters

<table>
  <tr>
    <td><b>Parameter</b></td>
    <td><b>Description</b></td>
    <td><b>Details</b></td>
  </tr>
  <tr>
    <td><b>inbox_id</b></td>
    <td>inbox ID (identifier)</td>
    <td>required</td>
  </tr>
</table>


### Errors

- <code>404</code> - Inbox not found

### Example
**Request**

    DELETE /api/v1/inboxes/5500b5dc589560c25a4a7eb2

**Return**

    {
        "createdAt": "2015-03-08T15:32:16.810Z",
        "name": "test1",
        "password": "9fc9e3f356c44e",
        "timestamp": "1425828736810",
        "updatedAt": "2015-03-21T18:16:32.792Z",
        "username": "8eb635a4bc08e0ab",
        "id": "5500b5dc589560c25a4a7eb2"
    }


## Clean all messages (emails) from inbox

    PATCH /api/v1/inboxes/:inbox_id/clean

### Parameters

<table>
  <tr>
    <td><b>Parameter</b></td>
    <td><b>Description</b></td>
    <td><b>Details</b></td>
  </tr>
  <tr>
    <td><b>inbox_id</b></td>
    <td>inbox ID (identifier)</td>
    <td>required</td>
  </tr>
</table>


### Errors

- <code>404</code> - Inbox not found

### Example
**Request**

    PATCH /api/v1/inboxes/550db7f0292ab52446439d60/clean

**Return**

    {
        "messages": [],
        "name": "1112",
        "username": "7b228cc7d70085d6",
        "password": "920ecb347fbcfe",
        "timestamp": "1426962416269",
        "createdAt": "2015-03-21T18:26:56.269Z",
        "updatedAt": "2015-03-21T18:26:56.270Z",
        "id": "550db7f0292ab52446439d60",
        "messages_count": 0,
        "messages_unread_count": 0,
        "messages_last_sent": null
    }
    
    
## Mark all messages (emails) as read

    PATCH /api/v1/inboxes/:inbox_id/all_read

### Parameters

<table>
  <tr>
    <td><b>Parameter</b></td>
    <td><b>Description</b></td>
    <td><b>Details</b></td>
  </tr>
  <tr>
    <td><b>inbox_id</b></td>
    <td>inbox ID (identifier)</td>
    <td>required</td>
  </tr>
</table>


### Errors

- <code>404</code> - Inbox not found

### Example
**Request**

    PATCH /api/v1/inboxes/550db7f0292ab52446439d60/all_read

**Return**

    {
        "messages": [],
        "name": "1112",
        "username": "7b228cc7d70085d6",
        "password": "920ecb347fbcfe",
        "timestamp": "1426962416269",
        "createdAt": "2015-03-21T18:26:56.269Z",
        "updatedAt": "2015-03-21T18:26:56.270Z",
        "id": "550db7f0292ab52446439d60",
        "messages_count": 0,
        "messages_unread_count": 0,
        "messages_last_sent": null
    }


## Reset inbox credentials

    PATCH /api/v1/inboxes/:inbox_id/reset_credentials

### Parameters

<table>
  <tr>
    <td><b>Parameter</b></td>
    <td><b>Description</b></td>
    <td><b>Details</b></td>
  </tr>
  <tr>
    <td><b>inbox_id</b></td>
    <td>inbox ID (identifier)</td>
    <td>required</td>
  </tr>
</table>


### Errors

- <code>404</code> - Inbox not found

### Example
**Request**

    PATCH /api/v1/inboxes/550db7f0292ab52446439d60/reset_credentials

**Return**

    {
        "createdAt": "2015-03-11T21:38:36.378Z",
        "name": "999",
        "password": "3f221f9459936f",
        "timestamp": "1426109916378",
        "updatedAt": "2015-03-21T19:16:40.136Z",
        "username": "afca784c2a8499fa",
        "id": "550db7f0292ab52446439d60"
    }


# Messages

Describes <code>Messages</code> object.

## Get messages from inbox.

    GET /api/v1/inboxes/:inbox_id/messages

### Parameters

<table>
  <tr>
    <td><b>Parameter</b></td>
    <td><b>Description</b></td>
    <td><b>Details</b></td>
  </tr>
  <tr>
    <td><b>inbox_id</b></td>
    <td>inbox ID (identifier)</td>
    <td>required</td>
  </tr>
</table>

### Errors

- _None_

### Example

**Request**

    GET /api/v1/inboxes/54faa5bcdc64b8b975a329a6/messages

**Return**

    [
        {
          "inboxes": "54faa5bcdc64b8b975a329a6",
          "username": "257b4a0177ea9591",
          "password": "b809c2fc8601e7",
          "mail": {
            "html": "<div>asdasd</div>",
            "text": ",e,e,e,e,",
            "headers": {
              "content-type": "multipart/alternative; boundary=\"----sinikael-?=_1-14269658635030.7619828174356371\"",
              "from": "support@mailcap.io",
              "to": "test@mailcap.io",
              "subject": "Sat Mar 21 2015 21:24:23 GMT+0200 (EET)",
              "x-mailer": "nodemailer (1.3.2; +http://www.nodemailer.com; SMTP/1.0.2[client:1.2.0])",
              "date": "Sat, 21 Mar 2015 19:24:23 +0000",
              "message-id": "<1426965863571-bdcb2996-b0084442-8e1ddaa2@mailcap.io>",
              "mime-version": "1.0"
            },
            "subject": "Sat Mar 21 2015 21:24:23 GMT+0200 (EET)",
            "messageId": "1426965863571-bdcb2996-b0084442-8e1ddaa2@mailcap.io",
            "priority": "normal",
            "from": [
              {
                "address": "support@mailcap.io",
                "name": ""
              }
            ],
            "to": [
              {
                "address": "test@mailcap.io",
                "name": ""
              }
            ],
            "date": "2015-03-21T19:24:23.000Z"
          },
          "read": false,
          "timestamp": "1426965863653",
          "createdAt": "2015-03-21T19:24:23.659Z",
          "updatedAt": "2015-03-21T19:24:23.659Z",
          "id": "550dc5671e9d05217e7c0af2"
        }
    ]
  
  
## Get one message from inbox

    GET /api/v1/inboxes/:inbox_id/messages/:message_id

### Parameters

<table>
  <tr>
    <td><b>Parameter</b></td>
    <td><b>Description</b></td>
    <td><b>Details</b></td>
  </tr>
  <tr>
    <td><b>inbox_id</b></td>
    <td>inbox ID (identifier)</td>
    <td>required</td>
  </tr>
  <tr>
    <td><b>message_id</b></td>
    <td>message ID (identifier)</td>
    <td>required</td>
  </tr>
</table>


### Errors

- <code>404</code> - Message not found

### Example
**Request**

    GET /api/v1/inboxes/54faa5bcdc64b8b975a329a6/messages/550dc5671e9d05217e7c0af2

**Return**

        {
          "inboxes": "54faa5bcdc64b8b975a329a6",
          "username": "257b4a0177ea9591",
          "password": "b809c2fc8601e7",
          "raw": "Content-Type: multipart/alternative;\r\n boundary=\"----sinikael-?=_1-14269658635030.7619828174356371\"\r\nFrom: support@mailcap.io\r\nTo: test@mailcap.io\r\nSubject: Sat Mar 21 2015 21:24:23 GMT+0200 (EET)\r\nX-Mailer: nodemailer (1.3.2; +http://www.nodemailer.com;\r\n SMTP/1.0.2[client:1.2.0])\r\nDate: Sat, 21 Mar 2015 19:24:23 +0000\r\nMessage-Id: <1426965863571-bdcb2996-b0084442-8e1ddaa2@mailcap.io>\r\nMIME-Version: 1.0\r\n\r\n------sinikael-?=_1-14269658635030.7619828174356371\r\nContent-Type: text/plain\r\nContent-Transfer-Encoding: 7bit\r\n\r\n,e,e,e,e,\r\n------sinikael-?=_1-14269658635030.7619828174356371\r\nContent-Type: text/html\r\nContent-Transfer-Encoding: 7bit\r\n\r\n<div>asdasd</div>\r\n------sinikael-?=_1-14269658635030.7619828174356371--",
          "mail": {
            "html": "<div>asdasd</div>",
            "text": ",e,e,e,e,",
            "headers": {
              "content-type": "multipart/alternative; boundary=\"----sinikael-?=_1-14269658635030.7619828174356371\"",
              "from": "support@mailcap.io",
              "to": "test@mailcap.io",
              "subject": "Sat Mar 21 2015 21:24:23 GMT+0200 (EET)",
              "x-mailer": "nodemailer (1.3.2; +http://www.nodemailer.com; SMTP/1.0.2[client:1.2.0])",
              "date": "Sat, 21 Mar 2015 19:24:23 +0000",
              "message-id": "<1426965863571-bdcb2996-b0084442-8e1ddaa2@mailcap.io>",
              "mime-version": "1.0"
            },
            "subject": "Sat Mar 21 2015 21:24:23 GMT+0200 (EET)",
            "messageId": "1426965863571-bdcb2996-b0084442-8e1ddaa2@mailcap.io",
            "priority": "normal",
            "from": [
              {
                "address": "support@mailcap.io",
                "name": ""
              }
            ],
            "to": [
              {
                "address": "test@mailcap.io",
                "name": ""
              }
            ],
            "date": "2015-03-21T19:24:23.000Z"
          },
          "read": false,
          "timestamp": "1426965863653",
          "createdAt": "2015-03-21T19:24:23.659Z",
          "updatedAt": "2015-03-21T19:24:23.659Z",
          "id": "550dc5671e9d05217e7c0af2"
        }

## Find messages

    GET /api/v1/inboxes/:inbox_id/messages?search=:query

### Parameters

<table>
  <tr>
    <td><b>Parameter</b></td>
    <td><b>Description</b></td>
    <td><b>Details</b></td>
  </tr>
  <tr>
    <td><b>inbox_id</b></td>
    <td>inbox ID (identifier)</td>
    <td>required</td>
  </tr>
  <tr>
    <td><b>query</b></td>
    <td>query for search at fields or subject, 
    separator - ';'
    not - '!'
    like - '*'
    </td>
    <td>required</td>
  </tr>
</table>




### Errors

- <code>404</code> - Message not found

### Example
**Request**

    GET /api/v1/inboxes/54faa5bcdc64b8b975a329a6/messages?search=username:a375b8f0f3bd7223;mail.subject:!sadasd;mail.date:%3C=2015-07-01;mail.priority:norma,notnormal;user:7777

**Return**

        {
          "inboxes": "54faa5bcdc64b8b975a329a6",
          "username": "257b4a0177ea9591",
          "password": "b809c2fc8601e7",
          "raw": "Content-Type: multipart/alternative;\r\n boundary=\"----sinikael-?=_1-14269658635030.7619828174356371\"\r\nFrom: support@mailcap.io\r\nTo: test@mailcap.io\r\nSubject: Sat Mar 21 2015 21:24:23 GMT+0200 (EET)\r\nX-Mailer: nodemailer (1.3.2; +http://www.nodemailer.com;\r\n SMTP/1.0.2[client:1.2.0])\r\nDate: Sat, 21 Mar 2015 19:24:23 +0000\r\nMessage-Id: <1426965863571-bdcb2996-b0084442-8e1ddaa2@mailcap.io>\r\nMIME-Version: 1.0\r\n\r\n------sinikael-?=_1-14269658635030.7619828174356371\r\nContent-Type: text/plain\r\nContent-Transfer-Encoding: 7bit\r\n\r\n,e,e,e,e,\r\n------sinikael-?=_1-14269658635030.7619828174356371\r\nContent-Type: text/html\r\nContent-Transfer-Encoding: 7bit\r\n\r\n<div>asdasd</div>\r\n------sinikael-?=_1-14269658635030.7619828174356371--",
          "mail": {
            "html": "<div>asdasd</div>",
            "text": ",e,e,e,e,",
            "headers": {
              "content-type": "multipart/alternative; boundary=\"----sinikael-?=_1-14269658635030.7619828174356371\"",
              "from": "support@mailcap.io",
              "to": "test@mailcap.io",
              "subject": "Sat Mar 21 2015 21:24:23 GMT+0200 (EET)",
              "x-mailer": "nodemailer (1.3.2; +http://www.nodemailer.com; SMTP/1.0.2[client:1.2.0])",
              "date": "Sat, 21 Mar 2015 19:24:23 +0000",
              "message-id": "<1426965863571-bdcb2996-b0084442-8e1ddaa2@mailcap.io>",
              "mime-version": "1.0"
            },
            "subject": "Sat Mar 21 2015 21:24:23 GMT+0200 (EET)",
            "messageId": "1426965863571-bdcb2996-b0084442-8e1ddaa2@mailcap.io",
            "priority": "normal",
            "from": [
              {
                "address": "support@mailcap.io",
                "name": ""
              }
            ],
            "to": [
              {
                "address": "test@mailcap.io",
                "name": ""
              }
            ],
            "date": "2015-03-21T19:24:23.000Z"
          },
          "read": false,
          "timestamp": "1426965863653",
          "createdAt": "2015-03-21T19:24:23.659Z",
          "updatedAt": "2015-03-21T19:24:23.659Z",
          "id": "550dc5671e9d05217e7c0af2"
        }

## Delete message

    DELETE /api/v1/inboxes/:inbox_id/messages/:message_id

### Parameters

<table>
  <tr>
    <td><b>Parameter</b></td>
    <td><b>Description</b></td>
    <td><b>Details</b></td>
  </tr>
  <tr>
    <td><b>inbox_id</b></td>
    <td>inbox ID (identifier)</td>
    <td>required</td>
  </tr>
  <tr>
    <td><b>message_id</b></td>
    <td>message ID (identifier)</td>
    <td>required</td>
  </tr>
</table>


### Errors

- <code>404</code> - Message not found

### Example
**Request**

    DELETE /api/v1/inboxes/54faa5bcdc64b8b975a329a6/messages/550dc5671e9d05217e7c0af2

**Return**

        {
          "inboxes": "54faa5bcdc64b8b975a329a6",
          "username": "257b4a0177ea9591",
          "password": "b809c2fc8601e7",
          "raw": "Content-Type: multipart/alternative;\r\n boundary=\"----sinikael-?=_1-14269658635030.7619828174356371\"\r\nFrom: support@mailcap.io\r\nTo: test@mailcap.io\r\nSubject: Sat Mar 21 2015 21:24:23 GMT+0200 (EET)\r\nX-Mailer: nodemailer (1.3.2; +http://www.nodemailer.com;\r\n SMTP/1.0.2[client:1.2.0])\r\nDate: Sat, 21 Mar 2015 19:24:23 +0000\r\nMessage-Id: <1426965863571-bdcb2996-b0084442-8e1ddaa2@mailcap.io>\r\nMIME-Version: 1.0\r\n\r\n------sinikael-?=_1-14269658635030.7619828174356371\r\nContent-Type: text/plain\r\nContent-Transfer-Encoding: 7bit\r\n\r\n,e,e,e,e,\r\n------sinikael-?=_1-14269658635030.7619828174356371\r\nContent-Type: text/html\r\nContent-Transfer-Encoding: 7bit\r\n\r\n<div>asdasd</div>\r\n------sinikael-?=_1-14269658635030.7619828174356371--",
          "mail": {
            "html": "<div>asdasd</div>",
            "text": ",e,e,e,e,",
            "headers": {
              "content-type": "multipart/alternative; boundary=\"----sinikael-?=_1-14269658635030.7619828174356371\"",
              "from": "support@mailcap.io",
              "to": "test@mailcap.io",
              "subject": "Sat Mar 21 2015 21:24:23 GMT+0200 (EET)",
              "x-mailer": "nodemailer (1.3.2; +http://www.nodemailer.com; SMTP/1.0.2[client:1.2.0])",
              "date": "Sat, 21 Mar 2015 19:24:23 +0000",
              "message-id": "<1426965863571-bdcb2996-b0084442-8e1ddaa2@mailcap.io>",
              "mime-version": "1.0"
            },
            "subject": "Sat Mar 21 2015 21:24:23 GMT+0200 (EET)",
            "messageId": "1426965863571-bdcb2996-b0084442-8e1ddaa2@mailcap.io",
            "priority": "normal",
            "from": [
              {
                "address": "support@mailcap.io",
                "name": ""
              }
            ],
            "to": [
              {
                "address": "test@mailcap.io",
                "name": ""
              }
            ],
            "date": "2015-03-21T19:24:23.000Z"
          },
          "read": false,
          "timestamp": "1426965863653",
          "createdAt": "2015-03-21T19:24:23.659Z",
          "updatedAt": "2015-03-21T19:24:23.659Z",
          "id": "550dc5671e9d05217e7c0af2"
        }


## Update message attributes (right now available only read attribute for modification)

    PATCH /api/v1/inboxes/:inbox_id/messages/:message_id

### Parameters

<table>
  <tr>
    <td><b>Parameter</b></td>
    <td><b>Description</b></td>
    <td><b>Details</b></td>
  </tr>
  <tr>
    <td><b>inbox_id</b></td>
    <td>inbox ID (identifier)</td>
    <td>required</td>
  </tr>
  <tr>
    <td><b>message_id</b></td>
    <td>message ID (identifier)</td>
    <td>required</td>
  </tr>
</table>


### Errors

- <code>404</code> - Message not found

### Example
**Request**

    PATCH /api/v1/inboxes/54faa5bcdc64b8b975a329a6/messages/550dc5671e9d05217e7c0af2
    {
    	"read": false
    }

**Return**

        {
          "inboxes": "54faa5bcdc64b8b975a329a6",
          "username": "257b4a0177ea9591",
          "password": "b809c2fc8601e7",
          "raw": "Content-Type: multipart/alternative;\r\n boundary=\"----sinikael-?=_1-14269658635030.7619828174356371\"\r\nFrom: support@mailcap.io\r\nTo: test@mailcap.io\r\nSubject: Sat Mar 21 2015 21:24:23 GMT+0200 (EET)\r\nX-Mailer: nodemailer (1.3.2; +http://www.nodemailer.com;\r\n SMTP/1.0.2[client:1.2.0])\r\nDate: Sat, 21 Mar 2015 19:24:23 +0000\r\nMessage-Id: <1426965863571-bdcb2996-b0084442-8e1ddaa2@mailcap.io>\r\nMIME-Version: 1.0\r\n\r\n------sinikael-?=_1-14269658635030.7619828174356371\r\nContent-Type: text/plain\r\nContent-Transfer-Encoding: 7bit\r\n\r\n,e,e,e,e,\r\n------sinikael-?=_1-14269658635030.7619828174356371\r\nContent-Type: text/html\r\nContent-Transfer-Encoding: 7bit\r\n\r\n<div>asdasd</div>\r\n------sinikael-?=_1-14269658635030.7619828174356371--",
          "mail": {
            "html": "<div>asdasd</div>",
            "text": ",e,e,e,e,",
            "headers": {
              "content-type": "multipart/alternative; boundary=\"----sinikael-?=_1-14269658635030.7619828174356371\"",
              "from": "support@mailcap.io",
              "to": "test@mailcap.io",
              "subject": "Sat Mar 21 2015 21:24:23 GMT+0200 (EET)",
              "x-mailer": "nodemailer (1.3.2; +http://www.nodemailer.com; SMTP/1.0.2[client:1.2.0])",
              "date": "Sat, 21 Mar 2015 19:24:23 +0000",
              "message-id": "<1426965863571-bdcb2996-b0084442-8e1ddaa2@mailcap.io>",
              "mime-version": "1.0"
            },
            "subject": "Sat Mar 21 2015 21:24:23 GMT+0200 (EET)",
            "messageId": "1426965863571-bdcb2996-b0084442-8e1ddaa2@mailcap.io",
            "priority": "normal",
            "from": [
              {
                "address": "support@mailcap.io",
                "name": ""
              }
            ],
            "to": [
              {
                "address": "test@mailcap.io",
                "name": ""
              }
            ],
            "date": "2015-03-21T19:24:23.000Z"
          },
          "read": false,
          "timestamp": "1426965863653",
          "createdAt": "2015-03-21T19:24:23.659Z",
          "updatedAt": "2015-03-21T19:24:23.659Z",
          "id": "550dc5671e9d05217e7c0af2"
        }


# User

Describes <code>User</code> object.

## User resource

    GET /api/v1/user

### Parameters

- _None_

### Errors

- <code>404</code> - User not found

### Example

**Request**

    GET /api/v1/user

**Return**

    {
        createdAt: "2015-02-25T19:36:30.842Z",
        email: "support@mailcap.io",
        token: "118a6501fa46e3aa89f62530d099af97",
        updatedAt: "2015-03-14T22:10:52.862Z",
        username: "support"
    }

## Reset user API token

    PATCH /api/v1/user/reset_token

### Parameters

- _None_

### Errors

- <code>404</code> - User not found

### Example
**Request**

    PATCH /api/v1/user/reset_token

**Return**

    {
        createdAt: "2015-02-25T19:36:30.842Z",
        email: "support@mailcap.io",
        token: "118a6501fa46e3aa89f62530d099af97",
        updatedAt: "2015-03-14T22:10:52.862Z",
        username: "support"
    }

# Error codes

- <code>200 OK</code> It's all good bro, you hit the right endpoint with right credentials
- <code>201 Created</code> New object saved
- <code>302 Found</code> Wrong url, follow <code>Location</code>
- <code>400 Bad Request</code> Returns JSON with the error message
- <code>401 Unauthorized</code> Couldn't authenticate your request
- <code>403 Forbidden</code> Couldn't authenticate your request
- <code>404 Not Found</code> No such object
- <code>405 Method Not Allowed</code> Supplied HTTP method not allowed for this endpoint
- <code>500 Internal Server Error</code> Something went wrong
- <code>503 Service Unavailable</code> Your connection is being throttled or the service is down for maintenance

All error messages (response code 400 and up) in the responses follow the following pattern:

    {
        code: "404",
        message: "Not found",
        description: "Not found inbox"
    }

