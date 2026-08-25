---
title: "Special mail-tags"
post_status: publish
post_name: special-mail-tags
lang: en
taxonomy:
  category: [contact-form-7]
source:
  blog_id: 66
  post_id: 47
  guid: "http://import.local/2021/12/27/special-mail-tags/"
---

There may be times when you need more information than just the submitter’s input through contact form fields. For example, you may need to know the submitter’s IP address for security reasons. For such purposes, special mail-tags can be very helpful.
Unlike other mail-tags, special mail-tags are independent from form fields or the submitter’s input. You can place these special mail-tags anywhere mail-tags are allowed to be used, such as in the message body or other mail fields.
Special mail-tags for submissions#Special mail-tags for submissions
[\_remote\_ip] — This tag is replaced by the submitter’s IP address.
[\_user\_agent] — This tag is replaced by the submitter’s user agent (browser) information.
[\_url] — This tag is replaced by the URL of the page in which the contact form is placed.
[\_date] — This tag is replaced by the date of the submission.
[\_time] — This tag is replaced by the time of the submission.
[\_invalid\_fields] — This tag is replaced by the number of form fields with invalid input.
[\_serial\_number] — This tag is replaced by a numeric string whose value increments, so this tag can work as the serial number of each submission. Requires Flamingo 1.5+ be installed.
Post-related special mail-tags#Post-related special mail-tags
These special mail-tags provide information about the post that contains the contact form.
Be aware that these [\_post\_\*] tags work only when the contact form is placed inside post content. In cases where the contact form is outside of post content, such as when the contact form is placed in a sidebar widget or embedded in a theme’s template file, a blank text will replace the tag.
[\_post\_id] — This tag is replaced by the ID of the post.
[\_post\_name] — This tag is replaced by the name (slug) of the post.
[\_post\_title] — This tag is replaced by the title of the post.
[\_post\_url] — This tag is replaced by the permalink URL of the post.
[\_post\_author] — This tag is replaced by the author name of the post.
[\_post\_author\_email] — This tag is replaced by the author email of the post.
Site-related special mail-tags#Site-related special mail-tags
These special mail-tags provide information about the WordPress website on which you manage the contact forms. You’ll find them especially useful when you want to reuse the same set of contact form templates between many websites, because you are freed from manual modification of the site information for each website.
[\_site\_title] — This tag is replaced by the title of the website.
[\_site\_description] — This tag is replaced by the description (tagline) of the website.
[\_site\_url] — This tag is replaced by the home URL of the website.
[\_site\_admin\_email] — This tag is replaced by the email address of the primary admin user of the website.
User-related special mail-tags#User-related special mail-tags
These special mail-tags provide information about the current logged-in user.
Since these [\_user\_\*] tags work only when the submitter has an account on the WordPress site and is logged in, it is recommended to turn on the subscribers-only mode setting anytime you use these tags.
If you want to use these tags but don’t want to use the subscribers-only mode, explicitly turn on the nonce setting. Otherwise, the logged-in user data will be reset by the WP REST API, and a blank text will replace the tag.
[\_user\_login] — This tag is replaced by the login name of the user.
[\_user\_email] — This tag is replaced by the email address of the user.
[\_user\_url] — This tag is replaced by the website URL of the user.
[\_user\_first\_name] — This tag is replaced by the first name of the user.
[\_user\_last\_name] — This tag is replaced by the last name of the user.
[\_user\_nickname] — This tag is replaced by the nickname of the user.
[\_user\_display\_name] — This tag is replaced by the display name of the user.
Share this:FacebookTwitterLike this:Like Loading...
