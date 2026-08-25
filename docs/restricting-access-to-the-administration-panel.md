---
title: "Restricting access to the administration panel"
post_status: publish
post_name: restricting-access-to-the-administration-panel
lang: en
taxonomy:
  category: [contact-form-7]
source:
  blog_id: 66
  post_id: 39
  guid: "http://import.local/2021/12/27/restricting-access-to-the-administration-panel/"
---

In its default settings, Contact Form 7 allows all users except subscriber users to have access to the administration panel; but allows only administrator and editor users to edit contact forms. You might feel that you would want to change this setting to restrict access even more, so I will show you how to do this in this article.
For example, let’s change access to allow only administrator users access and editing rights. You can do this by editing your wp-config.php and inserting these lines:
define( 'WPCF7\_ADMIN\_READ\_CAPABILITY', 'manage\_options' );
define( 'WPCF7\_ADMIN\_READ\_WRITE\_CAPABILITY', 'manage\_options' );
WPCF7\_ADMIN\_READ\_CAPABILITY holds the minimum capability required for access to the administration panel, while WPCF7\_ADMIN\_READ\_WRITE\_CAPABILITY holds the minimum capability required for editing contact forms. Obviously WPCF7\_ADMIN\_READ\_WRITE\_CAPABILITY should be stricter than WPCF7\_ADMIN\_READ\_CAPABILITY, as you cannot edit contact forms without accessing the administration panel.
manage\_options is a capability that normally only administrator users have. So setting manage\_options to both WPCF7\_ADMIN\_READ\_CAPABILITY and WPCF7\_ADMIN\_READ\_WRITE\_CAPABILITY allows only those administrator users access and editing rights.
You can set any capabilities you wish to these constants to fine-tune the restrictions. If you want to learn further about WordPress’ Roles and Capabilities concepts, and to learn more about what capabilities are available, check WordPress support document.
Share this:FacebookTwitterLike this:Like Loading...
