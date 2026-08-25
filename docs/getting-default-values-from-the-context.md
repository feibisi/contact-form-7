---
title: "Getting default values from the context"
post_status: publish
post_name: getting-default-values-from-the-context
lang: en
taxonomy:
  category: [contact-form-7]
source:
  blog_id: 66
  post_id: 31
  guid: "http://import.local/2021/12/27/getting-default-values-from-the-context/"
---

The default value of an input field is usually derived from the form-tag’s value part. It is, however, possible to get the default values from the context within which the form is placed.
To do this, add default:{source} option to the form-tag from which you want to derive the default value. Available data sources are: get (HTTP GET variables), post (HTTP POST variables), and post\_meta (custom fields). Logged-in user information is also available.
For example, you have a field with a name “your-name”:
[text\* your-name]
To get the default value from HTTP GET variables, add default:get option to the form-tag:
[text\* your-name default:get]
The field will obtain its default value from the GET variable with the same name (“your-name”). Try this by accessing the URL of the page of the form with an additional query string:
http://example.com/contact/?your-name=John+Smith
If it works correctly, you should see “John Smith” in the field.
Using the same logic, the custom field value is used for the default value of the field if: you have default:post\_meta option in the form-tag; and the page containing the form has a custom field named “your-name”.
But what if you have two or more default options in a single form-tag? Let’s consider this form-tag’s case:
[text\* your-name default:get default:post\_meta "Your Name"]
This form-tag has two default options and a value “Your Name”. The options are evaluated from the first to the last. In this example, default:get is evaluated first. If the “your-name” GET variable has a value, it will be used for the default value. If that value is empty, default:post\_meta will be evaluated next. If both of these options do not have values, “Your Name” will be used.
Share this:FacebookTwitterLike this:Like Loading...
