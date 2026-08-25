---
title: "Styling contact form"
post_status: publish
post_name: styling-contact-form
lang: en
taxonomy:
  category: [contact-form-7]
source:
  blog_id: 66
  post_id: 52
  guid: "http://import.local/2021/12/27/styling-contact-form/"
---

How do I style contact form? This is a common question on the support forum. Contact Form 7 doesn’t provide any customization for styling. Editing CSS style sheets is the best method to style contact forms. In this article, I’ll show you some important steps for styling your contact forms. If you know about CSS, my explanation is simple. If you are not familiar with CSS, please learn CSS first with these informative websites:
Learning CSS – W3CCSS Tutorial – W3SchoolsLearn CSS | MDN – Mozilla Developer NetworkCSS Basics
Which style sheet should I edit?#Which style sheet should I edit?
Any style sheet is okay, but I recommend editing your theme’s main style sheet. It’s better not to edit style sheets in the plugin because your changes will be overwritten when the plugin is updated. Themes can be updated, but they are generally updated less frequently than plugins. If your theme is updated often, you might make a child theme and manage the style sheet in the child theme.
You can also use Additional CSS, and it has several advantages over modifying theme’s stylesheets directly.
Styling contact form fields#Styling contact form fields
Let’s see how we can style individual fields in a contact form. There are several types of input fields. The most common field is a single-line text input field so let’s add a style rule for it:
input[type="text"]
{
background-color: #fff;
color: #000;
width: 50%;
}
This selector matches all input elements whose type attribute has exactly the value text (i.e. single-line text input fields). Also, this style rule has three properties specifying white as background color, black as foreground (text) color, and 50% as width of field.
You may want to apply this style rule to other types of fields. Let’s add selectors for an email address input field and a multi-line text input area:
input[type="text"],
input[type="email"],
textarea
{
background-color: #fff;
color: #000;
width: 50%;
}
Now this style is applied to every part of your site. You may want to limit it to contact forms. Contact Form 7’s form has a wrapper element that has the wpcf7 class. You can limit the scope of target by adding ancestor selectors:
.wpcf7 input[type="text"],
.wpcf7 input[type="email"],
.wpcf7 textarea
{
background-color: #fff;
color: #000;
width: 50%;
}
See also:
Why does my email address input field look different than other text input fields?Custom layout for checkboxes and radio buttons
Styling specific fields#Styling specific fields
You might want to style only specific fields. First, add an id or class option to the form-tags of the fields that you want to style:
[text text-123 id:very-special-field]
Then add style rules using the id or class:
#very-special-field
{
color: #f00;
border: 1px solid #f00;
}
Styling whole of contact form#Styling whole of contact form
As I mentioned earlier, the top-level element of contact form has the wpcf7 class. To style the whole contact form, add style rules for the class selector:
.wpcf7
{
background-color: #f7f7f7;
border: 2px solid #0f0;
}
This style rule gives your contact forms a light gray background and green border.
See also: Can I add id and class attributes to a form element?
Styling response messages#Styling response messages
The response message at the bottom of a contact form by default has the wpcf7-response-output class, so you can apply a style rule to this class to style the response message.
To decide on the style based on the status of the contact form, refer to the form element’s class attribute. It should have a class that reflects the current status. Possible values are: init, sent, failed, aborted, spam, invalid, or unaccepted.
For an example of styling, see the following default style rules that Contact Form 7 5.2.2 applies to a response message:
.wpcf7 form .wpcf7-response-output {
margin: 2em 0.5em 1em;
padding: 0.2em 1em;
border: 2px solid #00a0d2; /\* Blue \*/
}
.wpcf7 form.init .wpcf7-response-output {
display: none;
}
.wpcf7 form.sent .wpcf7-response-output {
border-color: #46b450; /\* Green \*/
}
.wpcf7 form.failed .wpcf7-response-output,
.wpcf7 form.aborted .wpcf7-response-output {
border-color: #dc3232; /\* Red \*/
}
.wpcf7 form.spam .wpcf7-response-output {
border-color: #f56e28; /\* Orange \*/
}
.wpcf7 form.invalid .wpcf7-response-output,
.wpcf7 form.unaccepted .wpcf7-response-output {
border-color: #ffb900; /\* Yellow \*/
}
See also: Locating response message box anywhere
Styling validation error messages#Styling validation error messages
When a field has an invalid value, a validation error message appears under the field. As the element of a validation error message has the wpcf7-not-valid-tip class, you can use the class to style validation error messages.
Contact Form 7 5.2.2 applies the following style rule by default:
.wpcf7-not-valid-tip {
color: #dc3232;
font-size: 1em;
font-weight: normal;
display: block;
}
See also: Customizing validation error messages
Share this:FacebookTwitterLike this:Like Loading...
