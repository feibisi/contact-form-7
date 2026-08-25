---
title: "reCAPTCHA (v3) 验证码"
post_status: publish
post_name: recaptcha
lang: mixed
taxonomy:
  category: [contact-form-7]
source:
  blog_id: 66
  post_id: 35
  guid: "http://import.local/2021/12/27/recaptcha-v3/"
---

[reCAPTCHA](https://www.google.com/recaptcha/intro/v3.html)保护您免受垃圾邮件和其他类型的自动滥用。使用 Contact Form 7 的 reCAPTCHA 集成模块，您可以阻止垃圾邮件机器人提交的滥用表单。
reCAPTCHA API 的最新版本是 v3。联系表格 7 5.1 及更高版本使用此 reCAPTCHA v3 API。reCAPTCHA v3 在后台运行，因此用户无需阅读图像中的模糊文本，甚至无需勾选“我不是机器人”复选框。
注意： reCAPTCHA v3 的 API 密钥与 v2 的不同；v2 的密钥不适用于 v3 API。您需要再次注册您的站点以获取 v3 的新密钥。
如果您使用的是旧版本的 Contact Form 7，并且正在寻找有关 v2 API 的 reCAPTCHA 模块的信息，请参阅[reCAPTCHA (v2)](https://contactform7.com/recaptcha-v2/)。

#### 注册网站

要开始使用 reCAPTCHA，您首先需要注册 WordPress 站点。reCAPTCHA 是 Google 的服务，因此您需要一个 Google 帐户才能使用它。使用该帐户登录 Google，然后转到[我的 reCAPTCHA](https://www.google.com/recaptcha/admin)页面。您将看到一个简单的注册表，如下所示：
![我的 reCAPTCHA 页面的屏幕截图](/_images/screenshot-recaptcha-1-991x1024.webp)

我的 reCAPTCHA 页面

从类型选项中选择reCAPTCHA v3，然后在域字段中输入网站的域。
注册网站后，您将获得该网站的站点密钥和秘密密钥。
![reCAPTCHA 站点详细信息的屏幕截图，包括站点密钥和密钥](/_images/screenshot-recaptcha-2-1024x355.webp)

网站详情

接下来，移至 WordPress 管理屏幕并打开联系人 > 集成菜单页面。
![集成菜单页面的屏幕截图](/_images/screenshot-recaptcha-3-1024x608.webp)

集成菜单页面

您将在那里看到一个名为reCAPTCHA的框。单击框中的设置集成。它将显示输入字段Site Key和Secret Key。将您在上一步中收到的两个密钥复制粘贴到字段中，然后点击保存更改。
![输入 API 密钥后集成页面的屏幕截图](/_images/screenshot-recaptcha-4-1024x622.webp)

输入 API 密钥

现在，您的联系表单使用 reCAPTCHA 的分数来验证表单提交是来自人类还是垃圾邮件机器人。
reCAPTCHA v3 不需要验证码小部件（reCAPTCHA v2 中使用的“我不是机器人”复选框）即可工作，因此[recaptcha]不再需要表单标签。如果[recaptcha]在表单模板中找到表单标签，Contact Form 7 5.1 或更高版本将忽略它们并用空字符串替换它们。

#### 也可以看看

- [reCAPTCHA v3 常见问题](https://contactform7.com/faq-about-recaptcha-v3/)
