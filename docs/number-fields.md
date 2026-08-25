---
title: "Number fields"
post_status: publish
post_name: number-fields
lang: en
taxonomy:
  category: [contact-form-7]
source:
  blog_id: 66
  post_id: 21
  guid: "http://import.local/2021/12/27/number-fields/"
---

A number field is a field for numeric value input. Contact Form 7 3.4 and higher provides two types of form-tag for number fields: number and range. These work the same except that they provide different types of user interface.
The new form-tag types, number and range, correspond with the HTML5 input types number and range, respectively. Currently, only some modern browsers support these input types.
Even among modern browsers, there may be differences in how those input fields are rendered on screen. In most cases, a number input is rendered as a spinner control while a range input is rendered as a slider control.
Older browsers and some modern browsers don’t support these input types and just render them as traditional text input fields.
Number field#Number field
Both number and number\* are used for number input and accept numeric value. number\* is a required field.
OptionExamplesDescriptionmin:(num)min:10min attribute value of the input element. Allowed minimum value for this field.max:(num)max:99max attribute value of the input element. Allowed maximum value for this field.step:(num)step:3step attribute value of the input element. When minimum number is 10 and step is 3, acceptable inputs are 10, 13, 16, 19, …id:(id)id:fooid attribute value of the input element.class:(class)class:barclass attribute value of the input element. To set two or more classes, you can use multiple class: option, like [number your-text class:y2008 class:m01 class:d01].placeholderwatermark Use the value as placeholder text instead of as default value. watermark works as an alias of placeholder
These fields can have a zero or one value, and the value will be used as the default value of the input field.
Example:
[number\* your-number min:10 max:99 step:3 class:required "40"]
Range field#Range field
Both range and range\* are used for number input and accept numeric value. range\* is a required field.
OptionExamplesDescriptionmin:(num)min:10min attribute value of the input element. Allowed minimum value for this field.max:(num)max:99max attribute value of the input element. Allowed maximum value for this field.step:(num)step:3step attribute value of the input element. When minimum number is 10 and step is 3, acceptable inputs are 10, 13, 16, 19, …id:(id)id:fooid attribute value of the input element.class:(class)class:barclass attribute value of the input element. To set two or more classes, you can use multiple class: option, like [number your-text class:y2008 class:m01 class:d01].placeholderwatermark Use the value as placeholder text instead of as default value. watermark works as an alias of placeholder
These fields can have a zero or one value, and the value will be used as the default value of the input field.
Example:
[range\* your-range min:10 max:99 step:3 class:required "40"]
Share this:FacebookTwitterLike this:Like Loading...
