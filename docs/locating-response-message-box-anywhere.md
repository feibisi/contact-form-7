---
title: "Locating response message box anywhere"
post_status: publish
post_name: locating-response-message-box-anywhere
lang: en
taxonomy:
  category: [contact-form-7]
source:
  blog_id: 66
  post_id: 43
  guid: "http://import.local/2021/12/27/locating-response-message-box-anywhere/"
---

After a visitor of your blog submits the contact form, the visitor sees a response message from Contact Form 7, such as “Your message was sent successfully” or “Validation errors occurred.” I sometimes hear from users who tell me that the position of the response message is not good, and, in fact, sometimes their visitors miss the message entirely.
The response message is shown at the bottom of the form by default. You can change the location by putting a response message placeholder [response] inside the form. You can insert this [response] tag into any place of your choice. You can use it multiple times in a form. The response message will be shown within the placeholder after submission.
Demo
Note: This is a demo. This form doesn’t send a mail practically.
Your Name (required)
Subject
Your Message
Δ
View source of above form:
[response]
Your Name (required)
[text\* your-name]
Subject
[text your-subject]
Your Message
[textarea your-message]
[response]
[submit "Send"]
Share this:FacebookTwitterLike this:Like Loading...
