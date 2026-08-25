---
title: "Acceptance checkbox"
post_status: publish
post_name: acceptance-checkbox
lang: en
taxonomy:
  category: [contact-form-7]
source:
  blog_id: 66
  post_id: 26
  guid: "http://import.local/2021/12/27/acceptance-checkbox/"
---

An acceptance checkbox is a simple checkbox dedicated to confirming the submitter’s consent for a specific condition. Contact Form 7 provides the acceptance form-tag type to represent acceptance checkboxes.
To use an acceptance checkbox in your contact form, simply insert an [acceptance] form-tag into the Form tab panel field like this:
[acceptance your-consent] I consent to the conditions. [/acceptance]
Notice that, unlike other form-tag types, the [acceptance] tag has a closing tag ([/acceptance]) at the tail. The part between the opening and closing tags is the content of the form-tag. When you set content to an acceptance checkbox form-tag, it is interpreted as the condition for consent.
If you use Flamingo to store submission data to the database, the information about submitters’ consent will also be stored, and Flamingo allows you to do future reference.
By default, an acceptance checkbox works as a required field, so you can’t submit the form without selecting the checkbox. If you set the optional option explicitly, the checkbox works as an optional field. If you set the invert option, it will invert the behavior so, in this case, you can’t submit the form without clearing the checkbox.
OptionExamplesDescriptionid:(id)id:fooid attribute value of the input element.class:(class)class:barclass attribute value of the input element. To set two or more classes, you can use multiple class: option, like [acceptance accept-this class:y2008 class:m01 class:d01].optional The acceptance checkbox works as an optional field.invert Allow users to submit only if they clear the checkbox.default:on The checkbox is selected by default.
Demo
Note: This is a demo. This form doesn’t send a mail practically.
1) Default
Check here if you accept these terms.
2) Inverted
Uncheck here if you accept these terms.
3) Selected by default + Inverted
Uncheck here if you accept these terms.
Δ
View source of the preceding form:
1) Default
[acceptance accept-this-1] Check here if you accept these terms. [/acceptance]
2) Inverted
[acceptance accept-this-2 invert] Uncheck here if you accept these terms. [/acceptance]
3) Selected by default + Inverted
[acceptance accept-this-3 invert default:on] Uncheck here if you accept these terms. [/acceptance]
[submit "Send"]
Acceptance as validation#Acceptance as validation
By default, an acceptance checkbox is a different mechanism than general input validation, and it runs after all validation succeeds. You might want to change this behavior to make it work like other validation because you think it’s less confusing for submitters than the default behavior. In such cases, add this line to the Additional Settings section:
acceptance\_as\_validation: on
This setting makes all acceptance checkboxes in the form work like validation, and shows the usual validation error message next to the checkbox if the submitter doesn’t check the box.
See also
How to make privacy-friendly contact forms
Share this:FacebookTwitterLike this:Like Loading...
