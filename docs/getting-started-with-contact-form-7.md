---
title: "Contact Form 7 联系表单入门"
post_status: publish
post_name: getting-started-with-contact-form-7
lang: zh
taxonomy:
  category: [contact-form-7]
  post_tag: [cf7-start]
source:
  blog_id: 66
  post_id: 12
  guid: "http://import.local/2021/12/27/getting-started-with-contact-form-7/"
---

本指南介绍了 WordPress 的 Contact Form 7 插件。需要 WordPress 管理的基本知识。本教程通过各种示例说明了如何在页面上显示表单，以及如何自定义表单和邮件。

#### 显示表格

让我们从在您的页面上显示一个表单开始。首先，打开WordPress 管理屏幕上的联系 > 联系表单菜单。您可以在那里管理多个联系表格。
![联系表 7 的管理屏幕截图](/_images/FnqQMMdp5w2u7FIE-8D451.webp)
 
安装 Contact Form 7 插件后，您将看到一个名为“Contact form 1”的默认表单，以及如下代码：

```
[contact-form-7 id="1234" title="Contact form 1"]
```

复制此代码。然后，打开您希望在其中放置联系表格的页面（页面 > 所有页面）的编辑菜单。一种流行的做法是为联系表单页面创建一个名为“Contact”的页面。将您复制的代码粘贴到页面内容中。
联系表格 7 5.3及更高版本支持块编辑器的联系表格选择器块。此块允许您简单地从您定义的联系表格列表中选择一个联系表格，而不是复制和粘贴短代码。
![联系表单选择器块的屏幕截图](/_images/cf7-screenshot-4.webp)

联系表单选择器块的屏幕截图

 
联系表单短代码仍然可用，当您想要[添加自定义属性时](https://contactform7.com/faq/can-i-add-id-and-class-attributes-to-a-form-element/)，或者当您有太多联系表单无法在单个列表中显示时，您会发现它们非常有用。
现在您的联系表格设置已完成。您网站的访问者现在可以找到该表单并开始向您提交消息。
接下来，让我们看看如何自定义表单和邮件内容。

#### 自定义表单

您可能会觉得默认表单对您来说太简单了，并且想要向其中添加更多字段。您可以在[管理屏幕中](https://contactform7.com/admin-screen/)编辑表单模板。
要将字段添加到表单，请为它们制作标签并将它们插入到[“表单”选项卡面板中的表单模板中](https://contactform7.com/editing-form-template/)。您会在表单模板中发现不熟悉的代码，例如[text\* your-name]. 这些代码在联系表 7 的词汇表中称为“标签”。
标签的[语法](https://contactform7.com/tag-syntax/#form_tag "标签的工作原理")相当复杂，但别担心！你不必学习它。您可以使用[标签生成器工具](https://contactform7.com/editing-form-template/)生成任意数量的[标签](https://contactform7.com/editing-form-template/)。
标签中的第二个字是它的名字。例如，名称`[text* your-name]`为“您的姓名”。此名称很重要，因为它稍后会在您的邮件模板中使用。

#### 自定义邮件

您可以像使用表单模板一样[在“邮件”选项卡面板中](https://contactform7.com/setting-up-mail/)编辑[邮件](https://contactform7.com/setting-up-mail/)模板。您也可以在那里使用标签，但请注意邮件标签与表单标签不同。
您可以在邮件模板中使用的标签在括号中仅包含一个单词，看起来像[your-name]. 您应该知道这个“您的名字”与前面示例中提到的表单标签的名称相同。这两个标签具有相同的名称。
在邮件中，`[your-name]`将被用户的输入值替换，该值通过相应的表单字段提交，在本例中为`[text* your-name]`。

#### 也可以看看

- [管理员画面](https://contactform7.com/admin-screen/ "管理屏幕")
- [标签的工作原理](https://contactform7.com/tag-syntax/ "标签的工作原理")
- [设置邮件](https://contactform7.com/setting-up-mail/ "设置邮件")
