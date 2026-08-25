---
title: "Selectable recipient with pipes"
post_status: publish
post_name: selectable-recipient-with-pipes
lang: en
taxonomy:
  category: [contact-form-7]
source:
  blog_id: 66
  post_id: 44
  guid: "http://import.local/2021/12/27/selectable-recipient-with-pipes/"
---

Imagine that you are a webmaster of a company and you need a contact form on your site which will let the sender to select an email recipient. Let’s say that the options are the CEO of the company (ceo@example.com), the sales department (sales@example.com) and the support department (support@example.com).
You’ve been able to achieve this with Contact Form 7 in this way: first, make a drop-down menu or radio button for the selection (you can do this by inserting a form-tag such as:
[select your-recipient "ceo@example.com"
"sales@example.com"
"support@example.com"]
into the form template); second, enter a corresponding mail-tag [your-recipient] into the To field in the Mail tab panel. This ensures that the email is sent to the specific address that the sender selected.
However, there has been a problem with this. By using this procedure, the email addresses are revealed over the Internet and this is not good. These addresses could then become targets of evil spammers very quickly.
So, what you need is a way to allow senders to select from closed data safely. The pipe (‘|’) support is just for this very purpose.
Change the form-tag of the drop-down menu to:
[select your-recipient "CEO|ceo@example.com"
"Sales|sales@example.com"
"Support|support@example.com"]
If you insert a pipe (‘|’) character in the middle of the option value, only the part before the pipe will be open to the outside, and the part after the pipe will be used for mail replacement.
To get the value after pipe character, put the usual mail-tag corresponding to the form-tag ([your-recipient] in the case of the preceding example) in the mail templates. To get value before pipe, you can use [\_raw\_{field name}] ([\_raw\_your-recipient] in the case of the preceding example).
You can use this usage of pipe only in the drop-down menu values, radio buttons or checkboxes. If you don’t like this feature, you may define the constant WPCF7\_USE\_PIPE as false to disable it.
Share this:FacebookTwitterLike this:Like Loading...
