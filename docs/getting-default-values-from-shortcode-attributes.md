---
title: "Getting default values from shortcode attributes"
post_status: publish
post_name: getting-default-values-from-shortcode-attributes
lang: en
taxonomy:
  category: [contact-form-7]
source:
  blog_id: 66
  post_id: 33
  guid: "http://import.local/2021/12/27/getting-default-values-from-shortcode-attributes/"
---

Sometimes you may feel that it would be useful if you could use values from [contact-form-7 ...] shortcode attributes.
In such cases, you can use the default:shortcode\_attr form-tag option, which retrieves the field default value from shortcode attributes.
For example, let’s say you have a field named “destination-email” for the destination email address:
[email\* destination-email]
To get the default value from shortcode attributes, add the default:shortcode\_attr option to the form-tag:
[email\* destination-email default:shortcode\_attr]
Then, add an attribute with the same name as the field (“destination-email” in this case) into the shortcode for the contact form:
[contact-form-7 id="123" title="Contact Form" destination-email="xxxxxx@example.com"]
Is that all? Unfortunately, no; there is a necessary extra step.
Normally, a WordPress shortcode only takes predefined attributes, so you need to register the attribute beforehand.
Add the following code snippet to your theme’s functions.php file:
add\_filter( 'shortcode\_atts\_wpcf7', 'custom\_shortcode\_atts\_wpcf7\_filter', 10, 3 );
function custom\_shortcode\_atts\_wpcf7\_filter( $out, $pairs, $atts ) {
$my\_attr = 'destination-email';
if ( isset( $atts[$my\_attr] ) ) {
$out[$my\_attr] = $atts[$my\_attr];
}
return $out;
}
That’s all! You’ll see “xxxxxx@example.com” input in the field.
Share this:FacebookTwitterLike this:Like Loading...
