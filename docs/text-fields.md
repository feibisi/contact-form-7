---
title: "文本字段"
post_status: publish
post_name: text-fields
lang: zh
taxonomy:
  category: [contact-form-7]
source:
  blog_id: 66
  post_id: 20
  guid: "http://import.local/2021/12/27/text-fields/"
---

文本输入字段是联系表单中最常见的因素。您可能知道，HTML 有两种类型的文本输入字段元素：用于单行输入；和多行输入。
Contact Form 7 提供了几种类型的[表单标签](https://contactform7.com/tag-syntax/#form_tag)来表示这两种类型的 HTML 元素：[文本字段](#text)（text和text\*）；[电子邮件字段](#email)（email和email\*）；[电话号码字段](#tel)（tel和tel\*）；[URL 字段](#url)（url和url\*）；和[文本区域](#textarea)（textarea和textarea\*）。在本文中，我将向您展示有关这些表单标签的用法和语义的详细信息。

#### 文本域

两个text和text\*用于单行输入和接受任何形式的文字。它们之间的区别在于表示text\*必填字段。在联系表格 7 的约定中，所有类型的带有星号“\*”的标签表示这些都是必填字段。

| 选项 | 例子 | 描述 |
| --- | --- | --- |
| id:（ID） | id:foo | idinput元素的属性值。 |
| class:（班级） | class:bar | classinput元素的属性值。要设置两个或更多类，您可以使用多个class:选项，例如[text your-text class:y2008 class:m01 class:d01]. |
| minlength:(数量) | minlength:10 | 此输入字段允许[的最小长度](https://contactform7.com/max-min-length-options-and-character-count/)。 |
| maxlength:(数量) | maxlength:90 | 此输入字段允许[的最大长度](https://contactform7.com/max-min-length-options-and-character-count/)。 |
| size:(数量) | size:50 | size此输入字段的HTML 属性值。 |
| akismet:author |  | [使用 Akismet 的选项。](https://contactform7.com/spam-filtering-with-akismet/) |
| placeholder watermark |  | 将该值用作[占位符文本](https://contactform7.com/setting-placeholder-text/)而不是默认值。watermark作为 的别名工作placeholder。 |
| default:user\_login default:user\_first\_name default:user\_last\_name default:user\_nickname default:user\_display\_name |  | [用于检索登录用户信息作为字段默认值的选项。](https://contactform7.com/setting-default-values-to-the-logged-in-user/) |

这些字段的值可以为零或一，该值将用作输入字段的默认值。
例子：

```
[text* your-name class:required "John Smith"]
```

#### 电子邮件字段

这两个email和email\*是单行输入，只接受电子邮件地址。email\*是必填字段。

| 选项 | 例子 | 描述 |
| --- | --- | --- |
| id:（ID） | id:foo | idinput元素的属性值。 |
| class:（班级） | class:bar | classinput元素的属性值。要设置两个或更多类，您可以使用多个class:选项，例如[email your-email class:y2008 class:m01 class:d01]. |
| minlength:(数量) | minlength:10 | 此输入字段允许[的最小长度](https://contactform7.com/max-min-length-options-and-character-count/)。 |
| maxlength:(数量) | maxlength:90 | 此输入字段允许[的最大长度](https://contactform7.com/max-min-length-options-and-character-count/)。 |
| size:(数量) | size:50 | size此输入字段的HTML 属性值。 |
| akismet:author\_email |  | [使用 Akismet 的选项。](https://contactform7.com/spam-filtering-with-akismet/) |
| placeholder watermark |  | 将该值用作[占位符文本](https://contactform7.com/setting-placeholder-text/)而不是默认值。watermark作为 的别名工作placeholder。 |
| default:user\_email |  | [用于检索登录用户信息作为字段默认值的选项。](https://contactform7.com/setting-default-values-to-the-logged-in-user/) |

这些字段的值可以为零或一，该值将用作输入字段的默认值。
例子：

```
[email your-email "example@example.com"]
```

#### 网址字段

这两个url和url\*是单行输入，只接受URL。url\*是必填字段。

| 选项 | 例子 | 描述 |
| --- | --- | --- |
| id:（ID） | id:foo | idinput元素的属性值。 |
| class:（班级） | class:bar | classinput元素的属性值。要设置两个或更多类，您可以使用多个class:选项，例如[url your-url class:y2008 class:m01 class:d01]. |
| minlength:(数量) | minlength:10 | 此输入字段允许[的最小长度](https://contactform7.com/max-min-length-options-and-character-count/)。 |
| maxlength:(数量) | maxlength:90 | 此输入字段允许[的最大长度](https://contactform7.com/max-min-length-options-and-character-count/)。 |
| size:(数量) | size:50 | size此输入字段的HTML 属性值。 |
| akismet:author\_url |  | [使用 Akismet 的选项。](https://contactform7.com/spam-filtering-with-akismet/) |
| placeholder watermark |  | 将该值用作[占位符文本](https://contactform7.com/setting-placeholder-text/)而不是默认值。watermark作为 的别名工作placeholder。 |
| default:user\_url |  | [用于检索登录用户信息作为字段默认值的选项。](https://contactform7.com/setting-default-values-to-the-logged-in-user/) |

这些字段的值可以为零或一，该值将用作输入字段的默认值。
例子：

```
[url your-url "http://example.com"]
```

#### 电话号码字段

这两个tel和tel\*是单行输入，只接受电话号码。tel\*是必填字段。

| 选项 | 例子 | 描述 |
| --- | --- | --- |
| id:（ID） | id:foo | idinput元素的属性值。 |
| class:（班级） | class:bar | classinput元素的属性值。要设置两个或更多类，您可以使用多个class:选项，例如[url your-url class:y2008 class:m01 class:d01]. |
| minlength:(数量) | minlength:10 | 此输入字段允许[的最小长度](https://contactform7.com/max-min-length-options-and-character-count/)。 |
| maxlength:(数量) | maxlength:90 | 此输入字段允许[的最大长度](https://contactform7.com/max-min-length-options-and-character-count/)。 |
| size:(数量) | size:50 | size此输入字段的HTML 属性值。 |
| placeholder watermark |  | 将该值用作[占位符文本](https://contactform7.com/setting-placeholder-text/)而不是默认值。watermark作为 的别名工作placeholder。 |

这些字段的值可以为零或一，该值将用作输入字段的默认值。
例子：

```
[tel your-tel "123-456-7890"]
```

#### 文本区

这两个textarea和textarea\*是一个多行输入和接受任何形式的文本。textarea\*是必填字段。

| 选项 | 例子 | 描述 |
| --- | --- | --- |
| id:（ID） | id:foo | idtextarea元素的属性值。 |
| class:（班级） | class:bar | classtextarea元素的属性值。要设置两个或更多类，您可以使用多个class:选项，例如[textarea your-text class:y2008 class:m01 class:d01]. |
| minlength:(数量) | minlength:10 | 此输入字段允许[的最小长度](https://contactform7.com/max-min-length-options-and-character-count/)。 |
| maxlength:(数量) | maxlength:90 | 此输入字段允许[的最大长度](https://contactform7.com/max-min-length-options-and-character-count/)。 |
| placeholder watermark |  | 将该值用作[占位符文本](https://contactform7.com/setting-placeholder-text/)而不是默认值。watermark作为 的别名工作placeholder。 |

这些字段可以有零个或一个值，该值将用作输入字段的默认值。
例子：

```
[textarea your-message "your message here …"]
```

还有另一种方法可以为 textarea 字段设置默认值：

```
[textarea your-message]
 foo
 bar
[/textarea]
```

通过这种方式，您可以设置多行默认值。

#### 演示

注意：这是一个演示。这种形式实际上不发送邮件。
![](/_images/Screenshot2021-12-27-14.29.46.webp)
 
查看上述表格的来源：

```
您的姓名（必填）
[text* your-name size:30 maxlength:60]

您的邮箱（必填）
[email* your-email "yourmail@example.com"]

您的留言
[textarea your-message]
default value for a textarea
can be multi-line
like this
[/textarea]

[submit "发送"]
```
