---
title: "Date field"
post_status: publish
post_name: date-field
lang: en
taxonomy:
  category: [contact-form-7]
source:
  blog_id: 66
  post_id: 22
  guid: "http://import.local/2021/12/27/date-field/"
---

HTML5 has introduced date input type. Browsers supporting this input type render a date field as a calendar-style date picker UI that you choose a date from. Contact Form 7 supports date and date\* types of form-tag that correspond with date input type.
Currently, only some modern browsers support this date input type. Older browsers and some modern browsers including Firefox don’t support this input type and just render it as a traditional text input field. Fortunately, Contact Form 7 can provide a fallback for those browsers.
If a value is specified in a date field, the value must be in YYYY-MM-DD format (e.g. 2013-04-08) according to the HTML5 specification. This is in most cases you don’t need to care about because browser’s date picker UI will set a value in the correct format.
OptionExamplesDescriptionmin:(date)min:2013-01-01min attribute value of the input element. Allowed minimum value for this field. You can use a relative date format as well.max:(date)max:2013-12-31max attribute value of the input element. Allowed maximum value for this field. You can use a relative date format as well.step:(num)step:3step attribute value of the input element. When minimum date is 2013-01-01 and step is 3, acceptable inputs are 2013-01-01, 2013-01-04, 2013-01-07, …id:(id)id:fooid attribute value of the input element.class:(class)class:barclass attribute value of the input element. To set two or more classes, you can use multiple class: option, like [date your-date class:y2008 class:m01 class:d01].placeholderwatermark Use the value as placeholder text instead of as default value. watermark works as an alias of placeholder
These fields can have a zero or one value, and the value will be used as the default value of the input field.
Example:
[date\* your-date min:2013-01-01 max:2013-12-31 step:7 class:required "2013-04-01"]
Specifying a date with relative date formats#Specifying a date with relative date formats
As well as YYYY-MM-DD format, you can use relative date formats to specify a date used in a date or date\* form-tag. Contact Form 7 5.3 and later allows you to use all date formats that the DateTimeImmutable class supports.
Using this technique, you can specify a date with natural expressions—such as “next Friday”, seen in the following example form-tag:
[date date-123 "next Friday"]
When you use date formats in a form-tag option, be aware that you are not allowed to use a space in an option value (as a space is used as the delimiter for options) and that you need to use an underscore (\_) as substitute for a space. For example:
[date date-123 max:next\_Friday+7days "next Friday"]
Format date value in mail#Format date value in mail
As previously explained, if a value is specified in a date field, the value must be in YYYY-MM-DD format (e.g. 2013-04-08). When the value is inserted into mail template, the date format keeps by default. To change the format in mail, you can use a variant of mail-tag notation [\_format\_{field name} "{date format}"].
Example:
[\_format\_your-date "D, d M y"]
D, d, M, and y in the above example are date format character described in the manual page of PHP date() function. "D, d M y" will format 2013-04-08 as Mon, 08 Apr 13. As the format is affected by localization, with the same "D, d M y" format, 2013-04-08 will become 月, 08 4月 13 in Japanese-localized WordPress.
Share this:FacebookTwitterLike this:Like Loading...
