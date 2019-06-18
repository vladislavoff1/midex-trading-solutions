---
description: >-
  Chat system is an automatically moderated system for communication of platform
  users with administrators and with each other
---

# Chat system

## User interface

On the exchange page, users have the opportunity to read and write to the chat window located in the lower right corner of the terminal.

![Chat interface](../../.gitbook/assets/image%20%2835%29.png)

In addition, each language has its own unique chat room. Chat has two global tolerance settings:

* All or only KYC users can write 
* Users can write with any balance or positive \(from a certain amount\)

Chat shows the actual number of on-line users at the moment. 

User IDs in the chat do not match their personal ID in the system. This was done specifically for personal data security reasons.

## Administration

To manage the chat, an administration panel has been developed that provides the following functions:

### Communication with users

![Admin page on english chat](../../.gitbook/assets/image%20%2834%29.png)

On this screen, the administrator has the ability to:Reply to chat as administrator 

* Reply to chat as anonymous / any user.
* Clear chat history 
* Block user \(with blocking time\) 
* Delete specific message

A separate tab shows all chat messages in tabular form with detailed information on each message:

![&#x42D;&#x43A;&#x440;&#x430;&#x43D; &#x441;&#x43F;&#x438;&#x441;&#x43A;&#x430; &#x441;&#x43E;&#x43E;&#x431;&#x449;&#x435;&#x43D;&#x438;&#x439; &#x447;&#x430;&#x442;&#x430;](../../.gitbook/assets/image%20%283%29.png)

Chat messages table data:

* Unique Message ID 
* Username 
* User message 
* Real user ID 
* User type 
* Date and time of the message 
* User lock button 
* Delete message button

### Stop words filters

![Screen for filter words addition \(offensive words are blurred\)](../../.gitbook/assets/image%20%2810%29.png)

In order to prevent unwanted messages from entering the chat, a system has been created that interferes with their placement. In the filter, you can add words as a list or one by one.

### Chat user list

![User list](../../.gitbook/assets/image%20%2816%29.png)

This list includes all chat users who have ever written to the chat, their real ID is displayed, and the user is shown blocked or not. In case of blocking, the remaining time until automatic unlocking is shown.

 The chat includes anti-flood and anti-spam filters. The first of them is responsible for ensuring that the user could not “capture” the chat — there can be no more than 5 messages from one user in a chat in a row. Anti-spam, does not allow the message, the text of which coincides with the previous one.



