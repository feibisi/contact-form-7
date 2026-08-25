---
title: "其他设置"
post_status: publish
post_name: additional-settings
lang: zh
taxonomy:
  category: [contact-form-7]
source:
  blog_id: 66
  post_id: 18
  guid: "http://import.local/2021/12/27/additional-settings/"
---

您可以通过将特定格式的代码片段添加到联系表单[编辑器屏幕](https://contactform7.com/admin-screen/)的“附加设置”选项卡面板中，为每个联系表单添加附加设置。
默认情况下，Contact Form 7 支持以下类型的设置。

#### 仅限订阅者模式

```
subscribers_only: true
```

您可能希望确保只有登录用户才能提交您的联系表单。在这种情况下，请使用仅限订阅者模式。在此模式下，未登录用户无法提交联系表单，并且会看到一条消息，通知他们需要登录，而登录用户可以照常使用。
在仅限订阅者模式下，不会为联系表单提供反垃圾邮件验证，因为只有受欢迎的人才能使用它们。如果此假设不适用于您的站点，则仅限订阅者模式可能不是您的好选择。

#### 演示模式

```
demo_mode: on
```

如果您demo\_mode: on在“附加设置”字段中进行设置，则联系表单将处于演示模式。在这种模式下，联系表单将跳过发送邮件的过程，只显示“成功完成”作为响应消息。

#### 跳过邮件

```
skip_mail: on
```

该skip\_mail设置的工作方式与 几乎相同demo\_mode，但skip\_mail仅跳过邮件发送。与 不同demo\_mode，skip\_mail不会影响其他活动，例如使用 Flamingo 存储消息。

#### 验收作为验证

```
acceptance_as_validation: on
```

默认情况下，接受复选框的行为与其他类型的字段不同；即使未选中该框，它也不会显示验证错误消息。如果您acceptance\_as\_validation: on在“其他设置”字段中进行设置，则联系表单中的接受复选框的行为方式与其他表单字段相同。
有关详细信息，请参阅[接受复选框](https://contactform7.com/acceptance-checkbox/)。

#### 火烈鸟设置

您可以自定义[Flamingo](https://contactform7.com/save-submitted-messages-with-flamingo/)管理屏幕中显示的主题和发件人字段值。有关更多详细信息，请参阅[使用 Flamingo 保存提交的消息](https://contactform7.com/save-submitted-messages-with-flamingo/)。

#### 抑制消息存储

```
do_not_store: true
```

此设置告诉消息存储模块，例如 Flamingo，不要通过此联系表单存储消息。

#### JavaScript 代码

```
on_sent_ok: "alert('sent ok');"
on_submit: "alert('submit');"
```

如果设置on\_sent\_ok:后跟一行 JavaScript 代码，则可以告诉联系表单邮件发送成功时应执行的代码。同样，使用on\_submit:，您可以告诉在提交表单时应该执行的代码，而不管结果如何。
另请参阅：[使用 Google Analytics 跟踪表单提交](https://contactform7.com/tracking-form-submissions-with-google-analytics/)并[在提交后重定向到另一个 URL](https://contactform7.com/redirecting-to-another-url-after-submissions/)
**注意： `on_sent_ok`并`on_submit`已从联系表 7 5.0 中正式删除。您可以使用[DOM 事件](https://contactform7.com/dom-events/)代替这些设置。**
