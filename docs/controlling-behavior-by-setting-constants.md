---
title: "Controlling behavior by setting constants"
post_status: publish
post_name: controlling-behavior-by-setting-constants
lang: en
taxonomy:
  category: [contact-form-7]
source:
  blog_id: 66
  post_id: 48
  guid: "http://import.local/2021/12/27/controlling-behavior-by-setting-constants/"
---

Contact Form 7 allows you to control its behavior by setting some constant values.
The typical place to define constants is in the wp-config.php file. You will find that many lines defining constants such as, define('XXX', 'xxx'); exist in the file. You can append new lines after them. Note that your lines must be placed before the last line.
Example (wp-config.php):
8081828384858687888990919293define( 'WP\_DEBUG', false ); define ( 'WPCF7\_LOAD\_JS', false ); // Added to disable JS loadingdefine ( 'WPCF7\_LOAD\_CSS', false ); // Added to disable CSS loading /\* That's all, stop editing! Happy publishing. \*/ /\*\* Absolute path to the WordPress directory. \*/if ( ! defined( 'ABSPATH' ) ) {    define( 'ABSPATH', \_\_DIR\_\_ . '/' );} /\*\* Sets up WordPress vars and included files. \*/require\_once ABSPATH . 'wp-settings.php';
The rest of this post describes a variety of constants.
WPCF7\_LOAD\_JS
When the value of this constant is false (default: true), Contact Form 7 does not load the JavaScript on the front end. When the value of this constant is set as header, Contact Form 7 loads the JavaScript in the header instead of in the footer (default).
See also: Loading JavaScript and stylesheet only when it is necessary
WPCF7\_LOAD\_CSS
When the value of this constant is false (default: true), Contact Form 7 does not load the CSS stylesheet on the front end.
See also: Loading JavaScript and stylesheet only when it is necessary
WPCF7\_AUTOP
When the value of this constant is false (default: true), Contact Form 7 does not apply the “autop” filter to the form content. The “autop” filter replaces double line-breaks with paragraph elements.
WPCF7\_USE\_PIPE
When the value of this constant is false (default: true), Contact Form 7 disables its “pipe” feature, so that pipe character has no special meaning.
See also: Selectable recipient with pipes
WPCF7\_ADMIN\_READ\_CAPABILITY
The value of this constant holds the minimum capability required for access to the administration panel. The default value is edit\_posts.
See also: Restricting access to the administration panel
WPCF7\_ADMIN\_READ\_WRITE\_CAPABILITY
The value of this constant holds the minimum capability required for editing contact forms. The default value is publish\_pages. Obviously WPCF7\_ADMIN\_READ\_WRITE\_CAPABILITY should be stricter than WPCF7\_ADMIN\_READ\_CAPABILITY, as you cannot edit contact forms without accessing the administration panel.
See also: Restricting access to the administration panel
WPCF7\_UPLOADS\_TMP\_DIR
When this constant is defined, the value of the constant overrides the setting of directory path of the temporary folder for uploaded files.
See also: File uploading and attachment
Share this:FacebookTwitterLike this:Like Loading...
