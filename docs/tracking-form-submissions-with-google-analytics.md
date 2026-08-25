---
title: "Tracking form submissions with Google Analytics"
post_status: publish
post_name: tracking-form-submissions-with-google-analytics
lang: en
taxonomy:
  category: [contact-form-7]
source:
  blog_id: 66
  post_id: 42
  guid: "http://import.local/2021/12/27/tracking-form-submissions-with-google-analytics/"
---

If you use Google Analytics to monitor web traffic on your site, you may also want to track contact form submissions. In this article, I’ll introduce a simple way to track submissions with Google Analytics.
Note that the JavaScript code used in this article is based on the latest version of the Google Analytics library at the time of this post (analytics.js). If you use the legacy library (ga.js), you will need to change the code in the following examples according to Google’s guide.
First, take a look at the HTML source of your site and confirm that you have a code snippet like the following:
(function(i,s,o,g,r,a,m){i['GoogleAnalyticsObject']=r;i[r]=i[r]||function(){
(i[r].q=i[r].q||[]).push(arguments)},i[r].l=1\*new Date();a=s.createElement(o),
m=s.getElementsByTagName(o)[0];a.async=1;a.src=g;m.parentNode.insertBefore(a,m)
})(window,document,'script','//www.google-analytics.com/analytics.js','ga');
ga('create', 'UA-XXXXX-Y', 'auto');
ga('send', 'pageview');
If not, you haven’t finished installing the basic page tracking code for Google Analytics yet; install that first.
Event tracking#Event tracking
A form submission can be tracked as an event. To send a form submission event to Google Analytics, call the JavaScript function as follows:
ga( 'send', 'event', 'Contact Form', 'submit' );
You probably want to track a submission event only when mail has been sent successfully. Contact Form 7 triggers wpcf7mailsent custom DOM event when it has sent mail, so let’s call the function within an event handler the following:
document.addEventListener( 'wpcf7mailsent', function( event ) {
ga( 'send', 'event', 'Contact Form', 'submit' );
}, false );
The final step is inserting this JavaScript code snippet into the HTML header () of each page. You can edit your theme’s header.php template, or you can use wp\_head action hook from the theme’s functions.php.
You of course need to wrap the code with tag when you embed script code into HTML:
document.addEventListener( 'wpcf7mailsent', function( event ) {
ga('send', 'event', 'Contact Form', 'submit');
}, false );
If you have set up everything correctly, Google Analytics will track successful form submissions through contact forms as an event with Contact Form as the event category, and submit as the event action.
To verify this is working correctly, you can check the Behavior > Events > Overview report page on Google Analytics 24-48 hours after a submission; at that point, tracked events should be recorded there.
Note: The method using on\_sent\_ok hook is no longer recommended. This function is scheduled to be abolished by the end of 2017.
Share this:FacebookTwitterLike this:Like Loading...
