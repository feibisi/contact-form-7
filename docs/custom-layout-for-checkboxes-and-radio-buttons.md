---
title: "Custom layout for checkboxes and radio buttons"
post_status: publish
post_name: custom-layout-for-checkboxes-and-radio-buttons
lang: en
taxonomy:
  category: [contact-form-7]
source:
  blog_id: 66
  post_id: 40
  guid: "http://import.local/2021/12/27/custom-layout-for-checkboxes-and-radio-buttons/"
---

In its default settings, Contact Form 7 renders checkboxes and radio buttons as inline boxes. You can customize this using some form-tag options and simple CSS.
Reversing checkbox-label order
By default, Contact Form 7 renders a checkbox in front of its label like the following:
You can reverse this order by adding label\_first option to the checkbox tag.
[checkbox your-cb label\_first "Option 1" "Option 2" "Option 3"]
Rendering checkboxes as block instead of original inline
To render checkboxes as block boxes, add a line of CSS style rule to your theme’s stylesheet:
1span.wpcf7-list-item { display: block; }
Rendering checkboxes as a table
To render checkboxes as a table, add these CSS style rules to your theme’s stylesheet:
12span.wpcf7-list-item { display: table-row; }span.wpcf7-list-item \* { display: table-cell; }
(Combined with label\_first option)
See also
Checkboxes, radio buttons and menusStyling contact form
Share this:FacebookTwitterLike this:Like Loading...
