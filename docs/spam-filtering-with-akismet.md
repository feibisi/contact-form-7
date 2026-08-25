---
title: "Spam filtering with Akismet"
post_status: publish
post_name: spam-filtering-with-akismet
lang: en
taxonomy:
  category: [contact-form-7]
source:
  blog_id: 66
  post_id: 38
  guid: "http://import.local/2021/12/27/spam-filtering-with-akismet/"
---

Spammers target everything and your contact forms are no exception.
Contact Form 7 provides several spam protection modules; we recommend utilizing different types in combination.
Akismet is a powerful anti-spam service provided by Automattic that protects your contact forms. Spam filtering with Akismet forms the centerpiece of our spam prevention strategy.
Activating Akismet#Activating Akismet
The first step is to activate the Akismet plugin. Since the plugin package of Akismet is bundled with WordPress, there is no need to manually install it. Move to the Plugins menu and simply activate the plugin titled Akismet Anti-Spam.
You need an API key to use Akismet. If you use it on a personal blog, you can get an API key for free. For corporate or commercial sites, paid subscriptions are available.
For people considering the paid subscriptions, we recommend Jetpack “Personal” or upper plans. Jetpack is the total solution package for WordPress and is provided by the same company as Akismet. In addition to Jetpack’s wide variety of features, the “Personal” and upper plans include an Akismet subscription that is equivalent to the Akismet “Plus” plan.
Deploying Akismet in a contact form#Deploying Akismet in a contact form
The primary purpose of Akismet is to protect WordPress comment forms. To use Akismet to protect Contact Form 7, you need to give specific options to input fields (form-tags).
There are three Akismet-related options:
akismet:author
You give this option to the field where submitters input their names.
Example: [text\* your-name akismet:author]
akismet:author\_email
You give this option to the field where submitters input their email addresses.
Example: [email\* your-email akismet:author\_email]
akismet:author\_url
You give this option to the field where submitters input the URL of their websites.
Example: [text your-url akismet:author\_url]
To deploy Akismet in a contact form, use one or more of these options in the form. To get accurate results, you are advised to use as many options as possible.
Where Akismet is deployed, Contact Form 7 sends data to Akismet when a user submits the form. The data are composed of all user inputs (not only the fields with an akismet:\* option) and variables from the environments. Akismet will verify the data to respond with a “spam” or “ham” answer.
If a “spam” answer is the response, Contact Form 7 will suspend the email and show a message saying, “There was an error trying to send your message,” surrounded by an orange border.
Testing the spam filtering#Testing the spam filtering
To test if the spam filtering is working correctly, try inputting “viagra-test-123” into the name (akismet:author) field or “akismet-guaranteed-spam@example.com” into the email (akismet:author\_email) field, and submitting the form. With these magic words reserved for testing, Akismet must return a “spam” response. If it is working as expected, you’ll see an orange-bordered error message.
Reporting false detection#Reporting false detection
Automated spam filtering cannot be 100% accurate. False positives (ham incorrectly classified as spam) and false negatives (spam incorrectly classified as ham) will exist. When you find messages are treated incorrectly by Akismet, you can report the false detection. Akismet learns from the information you report, and the accuracy of the spam filtering algorithm will be improved.
To report false detections to Akismet, you need the Flamingo plugin activated because Contact Form 7 doesn’t come with the ability to store submission data into the database. You can view messages through contact forms in the Flamingo > Inbound Messages menu. Normal messages are in the Inbox list, and spam messages are in the Spam list.
When you find a message in the Inbox list that should have been marked as spam, open the message and change the Status to Spam. Flamingo automatically sends a false negative report to the Akismet API. Likewise, change the status to Not Spam when you find a normal message in the Spam list. Flamingo properly reports false positives to Akismet.
Share this:FacebookTwitterLike this:Like Loading...
