---
title: "Setting default values to the logged-in user"
post_status: publish
post_name: setting-default-values-to-the-logged-in-user
lang: en
taxonomy:
  category: [contact-form-7]
source:
  blog_id: 66
  post_id: 32
  guid: "http://import.local/2021/12/27/setting-default-values-to-the-logged-in-user/"
---

You may need to create a contact form targeted at users with accounts on your WordPress site. You already have basic information about the user (name, e-mail, etc.) so asking users for this would be redundant.
You can set the logged-in user’s information as the default value by adding several options to a text field.
OptionDescriptiondefault:user\_loginUser’s login namedefault:user\_emailUser’s email addressdefault:user\_urlUser’s site URLdefault:user\_first\_nameUser’s first namedefault:user\_last\_nameUser’s last namedefault:user\_nicknameUser’s nicknamedefault:user\_display\_nameUser’s display name
Example:
Your Name: [text\* your-name default:user\_display\_name]
Your E-mail: [email\* your-email default:user\_email]
Users who are logged in will notice that the basic information is already completed.
Share this:FacebookTwitterLike this:Like Loading...
