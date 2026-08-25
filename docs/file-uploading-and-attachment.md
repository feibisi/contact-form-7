---
title: "File uploading and attachment"
post_status: publish
post_name: file-uploading-and-attachment
lang: en
taxonomy:
  category: [contact-form-7]
source:
  blog_id: 66
  post_id: 24
  guid: "http://import.local/2021/12/27/file-uploading-and-attachment/"
---

In this post, I will explain the file uploading and attachment feature of Contact Form 7. With this feature, you can allow your users to upload their files via your form, and then an email with attachments of the files is sent to you.
To set up, two steps are needed: 1) Add file uploading fields in your form, 2) Set up your mail settings to attach the uploaded files. The two steps will be explained in the rest of this post.
Adding file uploading fields in your form#Adding file uploading fields in your form
Like for other types of form fields, Contact Form 7 provides form-tags for file uploading fields ( in HTML): file and file\*. file\* is a required field and requires the user to upload a file.
OptionExamplesDescriptionid:(id)id:fooid attribute value of the input element.class:(class)class:barclass attribute value of the input element. To set two or more classes, you can use multiple class: option, like [file your-file class:y2008 class:m01 class:d01].filetypes:(filetypes)filetypes:gif|png|jpg|jpegAcceptable file types. List the file extensions after filetypes:, and separate them with ‘|’ (pipe) character when you set multiple file types.limit:(num)limit:1048576limit:1024kblimit:1mbLimit the max file size acceptable. You can use kb (kilo byte) or mb (mega byte) suffix optionally. If you omit suffix, the number means bytes. Note that you can’t use a decimal point in it (i.e., like this: [file your-file limit:1.5mb]) and it will be ignored if it exists.
Example:
[file your-file filetypes:pdf|txt limit:2mb]
Contact Form 7 applies default restrictions for file type and file size when you do not set the filetypes: and limit: (file size) options explicitly. Default acceptable file types (extensions) are: jpg, jpeg, png, gif, pdf, doc, docx, ppt, pptx, odt, avi, ogg, m4a, mov, mp3, mp4, mpg, wav, and wmv. Default acceptable file size is 1 MB (1048576 bytes).
Setting up file attachments with an email#Setting up file attachments with an email
To attach the uploaded files to the mail, put mail-tags corresponding to form-tags for file uploading fields into File attachments field in the Mail tab panel like shown below:
Screenshot of File Attachment field
In this example, the form-tag for the file uploading field is:
[file your-file filetypes:pdf]
Therefore, the corresponding mail-tag to this is:
[your-file]
Note that what you put in the File attachments field is [your-file] (mail-tag), not [file your-file filetypes:pdf] (this is not a mail-tag but a form-tag).
If you have multiple files uploaded and want to attach them into an email, simply line the mail-tags up in the File attachments field like this:
[your-file][your-another-file]
How tags work
Local file attachment#Local file attachment
Contact Form 7 supports local file attachment. You can put local file paths in the File attachments field and those files will be attached to the email as well as uploaded files.
Put a file path per line. When the path is not an absolute path, it will be treated as a relative path to the wp-content directory.
For security reasons, specifying files outside of the wp-content directory for email attachments is not allowed, so place the files in the wp-content or its subdirectory.
Example:
[your-file][your-another-file]
uploads/2013/08/08/boringguide.pdf
How your uploaded files are managed#How your uploaded files are managed
After a user uploads a file through your contact form, Contact Form 7 checks to see if: 1.) Any PHP errors have occurred; 2.) the file type and file size are valid; and then, if the check turns out okay, Contact Form 7 moves the uploaded file to a temporary folder. At this point, Contact Form 7 attaches the file to the mail and sends it. After these procedures, Contact Form 7 then removes the file from the temporary folder.
The location of the temporary folder is wp-content/uploads/wpcf7\_uploads by default. It may differ if you have changed upload path setting from wp-content/uploads.
This folder is created automatically, but sometimes it can fail. The most possible reason for this is that the parent folder doesn’t have sufficient writing permissions. In such cases, you can change the permissions or create a folder manually.
You can customize this directory path by defining the WPCF7\_UPLOADS\_TMP\_DIR constant like the following:
define( 'WPCF7\_UPLOADS\_TMP\_DIR', 'your-custom-tmp-dir' );
You can set the constant value to an absolute directory path or a relative path to the WordPress content directory (WP\_CONTENT\_DIR). Be aware that, even in cases where you set it to an absolute directory path, you can only specify a directory that is located under the content directory. Otherwise, the constant will be ignored.
Share this:FacebookTwitterLike this:Like Loading...
