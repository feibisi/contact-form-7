---
title: "Loading JavaScript and stylesheet only when it is necessary"
post_status: publish
post_name: loading-javascript-and-stylesheet-only-when-it-is-necessary
lang: en
taxonomy:
  category: [contact-form-7]
source:
  blog_id: 66
  post_id: 41
  guid: "http://import.local/2021/12/27/loading-javascript-and-stylesheet-only-when-it-is-necessary/"
---

In its default settings, Contact Form 7 loads its JavaScript and CSS stylesheet on every page. You might think it would be redundant or wasteful, and want to load them only on those pages that contain contact forms. I understand the feeling, but there is a technical difficulty for a plugin in knowing whether the page contains contact forms or not at the start of loading. However, I can show you a way to work around that.
Step 1: Stop loading the JavaScript and CSS stylesheet on all pages
When the value of WPCF7\_LOAD\_JS is set to false (default: true), Contact Form 7 does not load the JavaScript. You can set the value of this constant in your wp-config.php like this:
define( 'WPCF7\_LOAD\_JS', false );
Likewise, you can control the loading of the CSS stylesheet with WPCF7\_LOAD\_CSS. Contact Form 7 does not load the CSS stylesheet when the value of WPCF7\_LOAD\_CSS is false (default: true). You can set it in the wp-config.php like this:
define( 'WPCF7\_LOAD\_CSS', false );
Or, you can also disable the loading of the JavaScript and CSS by adding a few lines of code into your theme’s functions.php file, like this:
add\_filter( 'wpcf7\_load\_js', '\_\_return\_false' );
add\_filter( 'wpcf7\_load\_css', '\_\_return\_false' );
Now you have succeeded in stopping the loading of the JavaScript and CSS stylesheet, but, unfortunately, you’ve also killed them on pages that contain contact forms — so we really need to get them back on the right pages. So, the next step is what you’ll need to load the files on to the explicit pages in which you need them.
Step 2: Load the files on pages which contain contact forms
For example, let’s say you have a page named “Contact” and it is the only page that contains a contact form. And suppose that you have a template file for the “Contact” page named ‘contact.php’ in your theme folder. Now you will need to load Contact Form 7’s JavaScript and CSS stylesheet specifically on the “Contact” page.
To do this, you must edit the ‘contact.php’ template file and insert the following lines into it:
Note that wpcf7\_enqueue\_scripts() and wpcf7\_enqueue\_styles() must be called before wp\_head() is called.
Share this:FacebookTwitterLike this:Like Loading...
