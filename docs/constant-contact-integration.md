---
title: "Constant Contact 集成"
post_status: publish
post_name: constant-contact-integration
lang: mixed
taxonomy:
  category: [contact-form-7]
source:
  blog_id: 66
  post_id: 36
  guid: "http://import.local/2021/12/27/constant-contact-integration/"
---

**披露：此说明的作者是常联系会员，这意味着如果您决定通过插件作者的链接进行购买，插件作者将获得佣金，您无需支付任何费用。**
Constant Contact 集成模块允许您将通过您的联系表格收集的联系数据发送到 Constant Contact API。您可以通过几个简单的步骤创建可靠的电子邮件订阅服务。
您需要一个[Constant Contact](https://constant-contact.evyy.net/c/1293104/205991/3411)用户帐户才能使用此集成。如果您还没有帐户，请先[注册](https://constant-contact.evyy.net/c/1293104/205991/3411)以创建一个帐户，然后再继续。

- [连接到 API](#connecting-to-the-api)
- [联系人属性映射](#contact-properties-mapping)
- [获得同意](#obtaining-consent)
- [指定联系人列表](#contact-lists)

#### 连接到 API [#连接到 API](#connecting-to-the-api)

此集成模块使用 Constant Contact V3 API。要从您的 WordPress 网站开始使用 API，您首先需要注册一个应用程序以获取稍后将使用的 API 密钥和应用程序机密。
要注册应用程序，请移至[app.constantcontact.com 上](https://constant-contact.evyy.net/c/1293104/518422/3411)的“[我的应用程序”页面，](https://constant-contact.evyy.net/c/1293104/518422/3411)然后单击右上角的“新建应用程序”按钮。
系统会要求您提供应用程序名称。您可以随时更改名称，所以暂时将其命名为“Contact Form 7 Integration for (your site title) ”。
![Constant Contact 新应用模式的截图](/_images/screenshot-constant-contact-new-app-1024x544.webp)

新建应用程序模式对话框

单击保存，然后您将被定向到详细信息页面。
![详情页面截图](/_images/screenshot-constant-contact-app-details-1024x518.webp)

详情页面

在详细信息页面上，您将在第一个字段中找到API 密钥。单击API Key字段旁边的Generate Secret按钮以生成应用程序密钥。复制 API 密钥和应用程序机密，因为您将在下一步中使用它们。
![App Secret 模态对话框的屏幕截图](/_images/screenshot-constant-contact-app-secret-1024x530.webp)

App Secret 模态对话框

接下来，在浏览器的另一个选项卡中打开 WordPress 网站的管理屏幕。移动到Contact > Integration菜单页面，找到一个名为Constant Contact的框。
![WordPress 管理屏幕截图（联系 > 集成菜单）](/_images/screenshot-constant-contact-wp-admin-screen-1024x740.webp)

联系 > 集成菜单页面

单击设置集成按钮；它将显示一些输入字段。将您在上一步中复制的字符串粘贴到API Key和App Secret字段中。
![联系人 > 集成菜单页面的屏幕截图](/_images/screenshot-constant-contact-integration-box-1024x768.webp)

设置集成

您将在两个字段下找到Redirect URI只读字段。复制此字段值并将其粘贴到[app.constantcontact.com](https://constant-contact.evyy.net/c/1293104/518422/3411)上“详细信息”页面上的“重定向 URI”字段中。
![app.constantcontact.com 上详细信息页面的屏幕截图](/_images/screenshot-constant-contact-details-page-2-1024x555.webp)

粘贴重定向 URI 后的详细信息页面

在“详细信息”页面上更改字段值后，单击右上角的“保存”按钮。
现在，您几乎完成了必要的设置。返回WordPress 管理屏幕中的Contact > Integration菜单页面，然后单击Connect to the Constant Contact API按钮开始授权过程。
![Connect to the Constant Contact API 按钮的屏幕截图](/_images/screenshot-constant-contact-start-auth-1024x780.webp)

连接到 Constant Contact API 按钮

如果您已正确设置所有内容，您将被定向到 Constant Contact 登录页面（如果您尚未登录），并会被要求授权您注册的应用程序以访问您的 Constant Contact 帐户.
![授权屏幕截图](/_images/screenshot-constant-contact-oauth2-1024x827.webp)

授权画面

之后，您将被重定向回 WordPress，并发现框的边框颜色已更改为蓝色。蓝色边框表示已成功创建与 API 的连接。
![授权后的Constant Contact Integration框截图](/_images/screenshot-constant-contact-auth-completed-1024x757.webp)

授权完成

#### 联系人属性映射[#联系人属性映射](#contact-properties-mapping)

现在，您的联系表单和 Constant Contact API 已连接。
每次收到有效的表单提交时，Contact Form 7 都会向 Constant Contact API 发送一个请求，让 Constant Contact 根据提交将联系人数据添加到其数据库中。
Constant Contact的联系人数据由不同类型的属性组成，例如名字、姓氏、电子邮件地址、电话号码、职位、生日等。要构建对API的请求，Contact Form 7需要知道哪个输入字段联系表的哪个属性对应Constant Contact的联系数据的哪个属性。
Contact Form 7 使用以下基于名称的映射表来确定输入字段和联系人属性之间的对应关系。例如，如果[email\* your-email]表单中有form-tag (name: your-email)，则通过该字段的值将用于email\_address联系人的属性。

| 表单字段名称 | 联系物业 |
| --- | --- |
| your-first-name | first\_name |
| your-last-name | last\_name |
| your-name | first\_name和last\_name(\*1) |
| your-email | email\_address |
| your-job-title | job\_title |
| your-company-name | company\_name |
| your-birthday-month | birthday\_month |
| your-birthday-day | birthday\_day |
| your-birthday | birthday\_month和birthday\_day(\*2) |
| your-anniversary | anniversary |
| your-phone-number | phone\_numbers |
| your-address-street | street\_addresses.street |
| your-address-city | street\_addresses.city |
| your-address-state | street\_addresses.state |
| your-address-postal-code | street\_addresses.postal\_code |
| your-address-country | street\_addresses.country |

\*1 — 如果表单中没有your-first-nameoryour-last-name字段但有一个your-name字段，则your-name字段值的第一个单词将用于first\_name联系属性，其余的将用于last\_name属性。
\*2 — 如果表单中没有your-birthday-month和your-birthday-day字段，但有your-birthday一个日期值为 YYYY-MM-DD 格式的字段，则该值的月和日部分将分别用于birthday\_month和birthday\_day联系人属性。
在某些情况下，您可能觉得此映射不适合您的实际表单字段。对于这种情况，Contact Form 7 提供了wpcf7\_constant\_contact\_contact\_post\_request\_builder过滤器钩子。虽然它需要一些 PHP 编码来创建过滤器功能，但您可以使用此过滤器自定义联系人创建请求中的任何内容。

#### 获得同意[#获得同意](#obtaining-consent)

强烈建议您在将联系人数据添加到订阅列表之前获得联系表单提交者的明确同意。这不仅是因为未经同意收集和使用个人数据是非法的。这也是因为将电子邮件发送给非预期接收者会导致垃圾邮件投诉率很高。
对于检查提交者是否同意将其联系数据添加到 Constant Contact 订阅列表的表单字段，Contact Form 7 提供了consent\_for:constant\_contactform-tag 选项。您可以使用以下示例中的选项：

```
[接受您的同意可选consent_for:constant_contact]
将我添加到 Constant Contact 订阅列表。
[/验收]
```

如果您的联系表单中有此表单标签（[接受复选框](https://contactform7.com/acceptance-checkbox/)），则仅当提交者选中该复选框以确认他们的同意时，Contact Form 7 才会将联系数据发送到 Constant Contact API。

#### 指定联系人列表[#指定联系人列表](#contact-lists)

Constant Contact 允许您将收集到的联系人数据分组到联系人列表（也称为“电子邮件列表”或简称“列表”）中。
![描述如何管理联系人列表的 Constant Contact 仪表板的屏幕截图。](/_images/cf7-screenshot-2.webp)

常联系列表管理页面

Contact Form 7 的 Constant Contact Integration 支持为通过您的联系表格收集的新联系人指定联系人列表。
如果您还没有联系人列表，请转至“ [Constant Contact”仪表板](https://app.constantcontact.com/pages/contacts/ui#lists)并尝试创建您的第一个列表。然后，返回 WordPress 管理屏幕。在[联系表单编辑器屏幕中](https://contactform7.com/admin-screen/)，您会发现在那里添加了Constant Contact选项卡面板。在此选项卡面板中，如果您想通过此联系人表单向联系人列表添加新联系人，请选中联系人列表复选框，然后选择联系人列表。
![Constant Contact 选项卡面板的屏幕截图](/_images/cf7-screenshot-3.webp)

恒定接触选项卡面板
