---
title: "Save submitted messages with Flamingo"
post_status: publish
post_name: save-submitted-messages-with-flamingo
lang: en
taxonomy:
  category: [contact-form-7]
source:
  blog_id: 66
  post_id: 51
  guid: "http://import.local/2021/12/27/save-submitted-messages-with-flamingo/"
---

Contact Form 7 doesn’t store submitted messages anywhere. Therefore, you may lose important messages forever if your mail server has issues or you make a mistake in mail configuration.
Install a message storage plugin before this happens to you. Flamingo saves all messages through contact forms into the database. Flamingo is a free WordPress plugin created by the same author as Contact Form 7.
» Download Flamingo plugin from WordPress.org
Customizing Subject and From fields in messages#Customizing Subject and From fields in messages
In the Inbound Messages admin menu, you will see there are Subject and From fields. Those fields have the message’s subject, and submitter’s name and email address respectively.
By default, those fields retrieve values from Contact Form 7’s default input fields: your-subject, your-name, and your-email. Therefore, if you have modified your contact form and it doesn’t have the default input fields, the Subject and From fields don’t show correct values.
In such cases, try customizing those fields as the following:
Open the Additional Settings tab in the contact form editor page, and add lines like these:
flamingo\_email: "[the-email-field]"
flamingo\_name: "[the-name-field]"
flamingo\_subject: "[the-subject-field]"
You can use plain text and mail-tags in the value for each line. You can also use multiple mail-tags in a line; if you have input fields for first name and last name instead of a single name field, you may want to set up the flamingo\_name like this:
flamingo\_name: "[first-name-field] [last-name-field]"
Share this:FacebookTwitterLike this:Like Loading...
