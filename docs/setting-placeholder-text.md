---
title: "Setting placeholder text"
post_status: publish
post_name: setting-placeholder-text
lang: en
taxonomy:
  category: [contact-form-7]
source:
  blog_id: 66
  post_id: 30
  guid: "http://import.local/2021/12/27/setting-placeholder-text/"
---

Placeholder text is descriptive text displayed inside an input field until the field is filled. It disappears when you start typing in the field. Placeholder text is commonly used in current user interfaces so you have probably seen it before.
To set placeholder text in a field in your form, you only need to add a placeholder option and a text value to the form-tag representing the field.
[text your-name placeholder "Your name here"]
Δ
You can use the placeholder option in the following types of form tags: text, email, url, tel, textarea, number, range, date, and captchar.
The placeholder text you set in the form tag is output into HTML as the value of the placeholder attribute in the input field. For legacy browsers that don’t support HTML5’s placeholder attribute, Contact Form 7 also provides JavaScript-based placeholder implementation.
The placeholder option is available on Contact Form 7 3.4 and higher. Users of older versions can still use watermark instead of placeholder. In Contact Form 7 3.4 and higher, watermark is treated as an alias of placeholder so you don’t need to change watermark to placeholder when you update the plugin.
Share this:FacebookTwitterLike this:Like Loading...
