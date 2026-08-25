---
title: "为什么我的 AJAX 联系表单不能正常工作？"
post_status: publish
post_name: why-isnt-my-ajax-contact-form-working-correctly
lang: zh
taxonomy:
  category: [contact-form-7]
source:
  blog_id: 66
  post_id: 59
  guid: "http://import.local/2021/12/27/why-isnt-my-ajax-contact-form-working-correctly/"
---

Contact Form 7 支持 AJAX 提交。因此，Contact Form 7 中正确配置的联系表单的工作方式与以下演示表单完全相同。尝试在字段中输入任何文本并提交。

您的姓名（必填）
您的电子邮件（必填）
您的留言

它怎么样？它是否像您网站上的联系表一样工作？有些人可能会惊讶地注意到您的表单和这个演示表单之间的差异，并认为，“我的表单在提交后总是重新加载页面，但这个表单不会。”
如果您的表单无法像这个演示表单那样工作，则可能是 Contact Form 7 的 JavaScript 在您的网站上无法正常运行。我会告诉你一些可能的原因。

- JavaScript 文件未加载这是我最近看到的原因。这是由于您的主题模板缺少用于排队 JavaScript 的调用函数。所需的功能是wp\_head()和wp\_footer()，它们分别在header.php和 中footer.php，在大多数正确的主题中。
- 与其他 JavaScript 的冲突许多插件和主题加载自己的 JavaScript。其中一些可能创建不正确，因此与其他插件冲突。在大多数情况下，当发生此类冲突时，您可能能够通过浏览器的脚本控制台找到 JavaScript 错误。
- HTML 结构无效与其他 JavaScript 一样，Contact Form 7 的 JavaScript 遍历和操作 HTML 的结构。因此，如果原始 HTML 结构无效，它将无法工作。您可以使用 HTML 验证器检查您的 HTML 是否有效。在这种情况下，我建议使用[W3C 标记验证服务](https://validator.w3.org/)。
