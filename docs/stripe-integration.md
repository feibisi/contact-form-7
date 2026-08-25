---
title: "Stripe 集成"
post_status: publish
post_name: stripe-integration
lang: zh
taxonomy:
  category: [contact-form-7]
source:
  blog_id: 66
  post_id: 37
  guid: "http://import.local/2021/12/27/stripe-integration/"
---

Contact Form 7 的 Stripe 集成模块允许您将信用卡支付小工具添加到您的联系表格中。您可以通过简单的步骤开始收款。使用此模块无需额外费用。
您需要一个 Stripe 帐户才能集成。如果您还没有，请先[创建一个帐户](https://dashboard.stripe.com/register)。另外，请注意您需要一个支持 HTTPS 的站点才能使用此模块。

#### 连接到 API [#连接到 API](#connecting-to-the-api)

该模块使用[Stripe Elements 和 Stripe.js](https://stripe.com/docs/stripe-js)，并与 Stripe API 交互工作。要开始使用它，请先获取您的 API 密钥。

1. 登录到 Stripe 仪表板。
2. 转到[开发人员 > API 密钥](https://dashboard.stripe.com/apikeys)。
3. 复制实时模式的可发布密钥和秘密密钥。

然后，打开另一个浏览器选项卡并按照以下步骤操作：

1. 登录到 WordPress 仪表板。
2. 转到联系 > 集成。
3. 单击Stripe面板中的设置集成。
4. 将可发布密钥和密钥粘贴到面板的输入字段中。
5. 单击保存更改。

就这样。如果 API 与您的网站之间的连接已成功建立，您将在 Stripe 面板的边框周围看到蓝线。

#### 设置您的联系表格[#设置您的联系表格](#setting-up-your-contact-forms)

与 API 建立连接后，下一步是通过为 Stripe 支付小工具添加[表单标签](https://contactform7.com/tag-syntax/#form_tag)来设置联系表单。
![Stripe 支付小部件的屏幕截图](/_images/cf7-screenshot-1.webp)

Stripe 支付小部件的屏幕截图

联系表格 7 为[stripe]支付小部件提供了表单标签。以下是[stripe]form-tag的示例：

```
[stripe currency:usd amount:700 "Proceed to checkout" "Pay 7 USD"]
```

一个[stripe]表单标签由两个选项和两个值组成。
该currency选项表示付款货币。该值必须是[Stripe 支持](https://stripe.com/docs/currencies)的[三字母货币代码](https://stripe.com/docs/currencies)。
该amount选项是支付的金额。请注意，金额必须以货币的最小单位提供。例如，USD 的最小单位是 1 cent（不是 1 美元），所以currency:usd amount:700在上面的例子中会收取 7 美元（不是 700 美元）。
Stripe 对某些货币的收费金额有稍微复杂的规则。强烈建议您查阅[Stripe 的文档](https://stripe.com/docs/currencies)。
下面两个值（"Proceed to checkout"和"Pay 7 USD"上面例子中）是可选的，如果你设置了它们，它们将用作提交按钮的标签文本；第一个将在初始提交阶段使用，第二个将分别用于二级阶段。
由于[stripe]表单标签包含一个提交按钮，因此您不需要在同一表单中使用另一个提交按钮。如果您在付款表单中有[[submit]表单标签](https://contactform7.com/submit-button/)，则可以安全地将其删除。
付款完成后，将向买家发送收据电子邮件。默认情况下，“您的电子邮件”字段用于获取买家的电子邮件地址，因此建议在表单中包含“您的电子邮件”字段。
另一个有用的提示：向[电子邮件模板](https://contactform7.com/setting-up-mail/)添加一个[特殊的邮件标签](https://contactform7.com/special-mail-tags/) 。这将被一个指向 Stripe 付款页面的 URL 链接取代，您可以在其中获取有关付款的详细信息。[\_stripe\_payment\_link]

#### 安全考虑[#安全考虑](#security-considerations)

付款表格是诈骗者极具吸引力的目标。使用 Contact Form 7 提供的安全模块保护您的表单。至少，[reCAPTCHA](https://contactform7.com/recaptcha/)是支付表单的必备条件。也建议一起使用[Akismet](https://contactform7.com/spam-filtering-with-akismet/)。
不幸的是，一些骗子仍有可能通过严格的安全措施偷偷摸摸。Stripe 提供了可靠的[解决方案](https://stripe.com/docs/radar)和[手册，](https://stripe.com/docs/disputes)您可以在付款表格遭到滥用时使用。
