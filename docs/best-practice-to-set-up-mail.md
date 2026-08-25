---
title: "Best practice to set up mail"
post_status: publish
post_name: best-practice-to-set-up-mail
lang: en
taxonomy:
  category: [contact-form-7]
source:
  blog_id: 66
  post_id: 55
  guid: "http://import.local/2021/12/27/best-practice-to-set-up-mail/"
---

Setting up mail (header and message) properly is essential for successful mail delivery. In this article, I’ll describe how you can properly set up mail to maximize mail deliverability.
Avoid looking like spam
Mail service providers have been fighting relentless mail abuses like spam and spoofing. Since anti-abuse techniques aren’t flawless, there is always a possibility of false-positives; even if you are not a real spammer, behaving like a spammer can increase the likelihood of being treated that way.
Let’s consider the following situation. In the “From” header field, you can use an email address that has absolutely no connection to the domain of the site on which the contact form is placed. For instance, you can use your @yahoo.com address in the From field even when your site isn’t on yahoo.com. Consequently, the receiver sees an email claiming to be “From” yahoo.com, which is actually from a completely different server.
As you can do this, so can spammers — and they do. Therefore, if you use a From email address that does not belong on the site domain, especially if you haven’t implemented an authentication method (described later), it is difficult for mail service providers to distinguish your legitimate mail from spam.
Bottom line: in the From field, use an email address that belongs to the same domain as the site.
Specify Reply-to address#Specify Reply-to address
When you reply to email, the reply is normally sent to the address specified in the From field of the original mail. What if you didn’t want to receive replies at the From address?
In such cases, specify the address you want the receiver to reply to in the “Reply-To” header field of the original mail.
In the Contact Form 7 admin screen, you can set Reply-To in the Additional headers field in the Mail and Mail (2) sections.
Prepare a real “WordPress” email address
It is recommended you prepare a real wordpress@{your-site-domain} address on your host. Because the default mail template of Contact Form 7 uses this address in its From field, someone might try to send mail to this address. Some hosts also block outgoing mail from this address if it doesn’t exist.
WordPress also uses the wordpress@{your-site-domain} address in its notification mail, including comment notification and new user notification. It doesn’t hurt to make this address even if you don’t use Contact Form 7.
Utilize email authentication
Even if you set an email address belonging in the site domain in the From field, spammers can still send spoofed mail as if you sent it from your domain. As long as the possibility of email spoofing exists, the risk of mail service providers confusing your legitimate mail for spoofed mail remains.
To protect your mail from this risk, you can utilize email authentication methods including SPF and DKIM, which are supported by most major mail service providers. For detailed instruction about how to set up authentication methods, consult your provider’s support.
Make sure you have appropriate values in mail fields
Be careful when using values from optional form input fields. Are your mail header fields valid even when the values are empty?
Also, be careful not to make the message body empty or too short. It not only makes the mail look like spam, it makes mail sending function fail on some hosts.
See also
Setting up mailAdding Cc, Bcc and other mail headers
External links
WordPress emails are sent but not receivedAbout SPF records – Google Apps Administrator HelpAuthenticate email with DKIM – Google Apps Administrator HelpEmail service providers can’t send to / from Yahoo addressesDMARC.org – Domain-based Message Authentication, Reporting and Conformance
Share this:FacebookTwitterLike this:Like Loading...
