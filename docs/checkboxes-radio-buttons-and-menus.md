---
title: "Checkboxes, radio buttons, and menus"
post_status: publish
post_name: checkboxes-radio-buttons-and-menus
lang: en
taxonomy:
  category: [contact-form-7]
source:
  blog_id: 66
  post_id: 23
  guid: "http://import.local/2021/12/27/checkboxes-radio-buttons-and-menus/"
---

Contact Form 7 provides several types of form-tags for representing checkboxes, radio buttons, and drop-down menus. This article explains about the usage and semantics of these form-tags.
Checkboxes and radio buttons#Checkboxes and radio buttons
Both checkbox and checkbox\* represent a group of checkboxes ( in HTML). checkbox\* requires the user to select at least one of the boxes.
radio represents a group of radio buttons ( in HTML). Because a group of radio buttons is naturally required, a radio form-tag works as a required field. It is advised to preselect an option in a radio button group using the default:1 option.
OptionExamplesDescriptionid:(id)id:fooid attribute value of the wrapper element.class:(class)class:barclass attribute value of the wrapper element. To set two or more classes, you can use multiple class: option.default:(num)default:2default:1\_2\_3Preselected options. The integer following default: is the position in the order of items. 1 is the first one. If you want to make two or more items selected, joint integers with underbar (\_), as default:1\_2\_3.label\_first By default, a checkbox or a radio button are put first, and a label last. By adding label\_first option, you can reverse them.use\_label\_element Wrap each checkbox and radio button with  tag.exclusive Make checkboxes exclusive. This means, when you select a checkbox in a group, others will be cleared, so the group accepts the zero-selected or one-selected state only. This is a JavaScript gimmick so doesn’t work without JavaScript. radio form-tags don’t support this option.free\_text Append a free input text field to the last item.data:(name)data:countriesGet the values from Listo.
These types of tags have one or more values, and the values will be used as the values and labels of the checkboxes or radio buttons.
Example:
[checkbox your-country "China" "India" "San Marino"]
Drop-down menus#Drop-down menus
Both select and select\* represent a drop-down menu ( in HTML). select\* requires the user to select at least one option from the menu.
OptionExamplesDescriptionid:(id)id:fooid attribute value of the select element.class:(class)class:barclass attribute value of the select element. To set two or more classes, you can use multiple class: option.default:(num)default:2default:1\_2\_3Preselected options. The integer following default: is the position in the order of items. 1 is the first one. If you want to make two or more items selected, joint integers with underbar (\_), as default:1\_2\_3.multiple Make the drop-down menu multi-selectable.include\_blank Insert a blank item into the top of options of this drop-down menu.first\_as\_label Use the first value as a label.data:(name)data:countriesGet the values from Listo.
These types of tags have one or more values, and the values will be used as options in the drop-down menu.
Example:
[select your-country "China" "India" "San Marino"]
See also
Selectable recipient with pipesCustom layout for checkboxes and radio buttons
Demo#Demo
Note: This is a demo form and it doesn’t send an email practically.
Select Country (required)
ChinaIndiaSan Marino
Select Sports
FootballTennisPole-vault
Select Fruit (required)
AppleBananaGrape
Select Browser (required)
---FirefoxSafariOperaLynx
Select Ghkdsjdf
fsdfsklgjfkvdrie
Δ
View source of the preceding form:Select Country (required)
[checkbox\* your-country use\_label\_element "China" "India" "San Marino"]
Select Sports
[radio your-sports label\_first default:2 "Football" "Tennis" "Pole-vault"]
Select Fruit (required)
[checkbox\* your-fruit exclusive "Apple" "Banana" "Grape"]
Select Browser (required)
[select\* your-browser include\_blank "Firefox" "Safari" "Opera" "Lynx"]
Select Ghkdsjdf
[select your-ghkdsjdf multiple "fsdfs" "klgjfk" "vdrie"]
[submit "Send"]
Share this:FacebookTwitterLike this:Like Loading...
