# FAQ

- [What is Mailcap?](#what-is-mailcap)
- [How do I integrate it with my application?](#how-do-i-integrate-it-with-my-application)
- [Why is Mailcap better than the other solutions?](#why-is-mailcap-better-than-the-other-solutions)
- [How does Mailcap render emails?](#how-does-mailcap-render-emails)
- [What does Mailcap do with &lt;style&gt; tag?](#what-does-mailcap-do-with-style-tag)
- [Can Mailcap show what email will look like in various email clients?](#can-mailcap-show-what-email-will-look-like-in-various-email-clients)
- [I've got a problem integrating Mailcap with my app, what should I do?](#ive-got-a-problem-integrating-mailcap-with-my-app-what-should-i-do)
- [What is the email size limit?](#what-is-the-email-size-limit)
- [What is the SMTP rate limit for inbox?](#what-is-the-smtp-rate-limit-for-inbox)
- [How do I delete my account?](#how-do-i-delete-my-account)

## What is Mailcap?
Mailcap is a solution that allows testing email notifications without sending them to the real users of your application. It also lets you view all your emails online, forward them to your regular mailbox!

## How do I integrate it with my application?
Simply specify Mailcap as an SMTP server in your application's settings (either QA or development environments) and track all your e-mail notifications online.

## Why is Mailcap better than the other solutions?
1. Extremely easy to set up:
  - no need to tune your mail server;
  - no need to clean up your database from the customers' email addresses;
  - no need to make any special tweaks in your application code.
2. Can be used for both development and staging purposes.
3. Is platform-independent. Since Mailcap uses SMTP (not some special platform-dependant libraries), you can use it with any programming language and framework.

## How does Mailcap render emails?
Mailcap renders emails in the same way browsers do, which means no additional stylesheet or CSS reset is applied by default. This makes Mailcap 99% Gmail/Hotmail/Yahoo Mail compatible, since all of these mail clients are rendering the same way.

## What does Mailcap do with &lt;style&gt; tag?
Mailcap doesn't rip the style tag out of the email templates.

## Can Mailcap show what email will look like in various email clients?
Mailcap is compatible with the web email clients. You can also forward emails to Outlook, Thunderbird, etc., and use these desktop clients to view them.

## I've got a problem integrating Mailcap with my app, what should I do?
Please send us an email at support@mailcap.io describing the issue; we'll try to help you ASAP.

## What is the email size limit?
The max size of an email including attachments is 10MB. Exceeding this limit causes the error: '552 5.3.4 Error: message too big'

## What is the SMTP rate limit for inbox?
- &#8734; inboxes
- ~ 75 emails/sec per inbox


## How do I delete my account?
Please send us an email with your request at support@mailcap.io providing your API token and email of your account which you want to delete.

